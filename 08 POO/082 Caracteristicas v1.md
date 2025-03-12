# Características v1 de la POO

En esta primera versión de este módulo vamos a aplicar algunas de las características que hemos visto en el apartado de [teoría](080%20Teoria.md)

**Herencia**: supongamos que nuestra aplicación gestiona tanto a los clientes como a los trabajadores de un supermercado. Además, no solo hay un tipo de trabajador, si no que tenemos el perfil de carnicero y de panadero

**Abstracción**: si pensamos, muchos atributos se compartirían entre las clases ya que todos tendrán su nombre, apellido, edad, etc. Todos tienen en común que son personas, por lo que podemos abstraer aquellos atributos y métodos comunes a una clase *Persona*

**Abstracción y polimorfismo**: además, también podemos abstraer atributos y métodos comunes de los trabajadores, como por ejemplo el salario, la acción de trabajar, etc.

Por último, al tener dos clases abstractas y genéricas, tenemos que pensar si esas mismas clases tienen sentido que se puedan instanciar

¿Tiene sentido que en la aplicación existan personas? No, porque una persona tiene que ser o un cliente o algún tipo de trabajador

De igual manera, ¿tiene sentido que en la aplicación existan trabajadores? No, porque un trabajador tiene que ser o carnicero o panadero

Para llegar a estas conclusiones, es necesario hacer un análisis previo de los requerimientos del sistema. Conviene hacer **diagramas UML** para tener claro las capas de abstracción y saber verdaderamente cuáles son dichos requerimientos

Una vez hecho el análisis, ¡vamos a picar!

Primero de todo, reusaremos la clase *Persona*, implementada en el apartado anterior de [fundamentos](081%20Fundamentos.md). Esta es la clase padre y la haremos abstracta para que no se puedan instanciar objetos de la clase *Persona*

```csharp
// Usar abstract para que no se puedan instanciar objetos de la clase
abstract class Persona(string nombre = "Anónimo", int edad = -1)
{
    public string Nombre { get; set; } = nombre;
    public int Edad { get; set; } = edad;

    public void SaludarA(Persona otro)
    {
        Console.WriteLine($"Hola {otro.Nombre}, me llamo {Nombre}");
    }

    override public string ToString()
    {
        return $"{Nombre}";
    }
}
```

Vamos a crear la clase *Cliente* (hija), que hereda de *Persona* (padre), con un atributo que será el dinero que dispone para comprar en el supermercado

```csharp
class Cliente(
    float dinero = 500f,
    string nombre = "Anónimo",
    int edad = -1
) : Persona(nombre, edad)
{
    public float Dinero { get; set; } = dinero;

    public void Comprar(float precio)
    {
        if (precio > Dinero)
        {
            Console.WriteLine($"Saldo ({Dinero}) insuficiente para comprar el producto que cuesta {precio} euros");
        } else {
            Dinero -= precio;
            Console.WriteLine($"{this}, te quedan {Dinero} euros. El articulo costaba: {precio} euros");
        }
    }

    public void Ingresar(float cantidad)
    {
        Dinero += cantidad;
        Console.WriteLine($"Has ingresado {cantidad} euros. Ahora tienes en total {Dinero} euros");
    }

    override public string ToString()
    {
        return $"C {base.ToString()}"; // Ponemos C y el ToString de la clase padre para diferenciar que la persona es un Cliente
    }
}
```

Vamos a probar la clase que hemos implementado en la clase cliente para ver que todo funciona correctamente

```csharp
var cliente = new Cliente(1000f, "Pablo", 27);

Console.WriteLine(cliente); // C Pablo
cliente.Comprar(500f); // Pablo, te quedan 500 euros
cliente.Comprar(501f); // Saldo (500) insuficiente para comprar el producto que cuesta 501 euros
cliente.Ingresar(2000f);
cliente.Comprar(501f); // Pablo, te quedan 1999 euros
```

A continuación, vamos a crear la clase *Trabajador* que hereda de *Persona*, con un atributo salario. Como hemos dicho, esta clase será abstracta, junto a su método trabajar, que también será abstracto ya que cada trabajador trabajará a su manera (**polimorfismo**)

```csharp
abstract class Trabajador(
    float salario = 1500f,
    string nombre = "Anónimo",
    int edad = -1
) : Persona(nombre, edad)
{
    public float Salario { get; set; } = salario;

    public void CobrarPagaExtra()
    {
        Console.WriteLine($"Este mes paga extra: {Salario * 2}");
    }

    // No tiene cuerpo de función, cada clase hija se encarga de su propia implementación
    public abstract void Trabajar();
}
```

Ahora implementaremos la clase *Carnicero* que hereda de *Trabajador*, que a su vez hereda de *Persona*

```csharp
class Carnicero(
    int cuchillos = 2,
    float salario = 1500f,
    string nombre = "Anónimo",
    int edad = -1
) : Trabajador(salario, nombre, edad)
{
    public float Cuchillos { get; set; } = cuchillos;

    override public void Trabajar()
    {
        Console.WriteLine($"Estoy cortando carne con mis {Cuchillos} cuchillo(s)");
    }

    override public string ToString()
    {
        return $"Ca {base.ToString()}";
    }
}
```

Vamos a probar que todo funcione correctamente

```csharp
var carnicero = new Carnicero(5, 2000f, "Pablo", 27);

Console.WriteLine(carnicero); // Ca Pablo
carnicero.Trabajar(); // Estoy cortando carne con mis 5 cuchillo(s)
carnicero.CobrarPagaExtra(); // Este mes paga extra: 4000 euretes
```

Y por último, nos queda la clase *Panadero*

```csharp
class Panadero(
    float temperatura = 35f,
    float salario = 1500f,
    string nombre = "Anónimo",
    int edad = -1
) : Trabajador(salario, nombre, edad)
{
    public float Temperatura { get; set; } = temperatura;

    override public void Trabajar()
    {
        Console.WriteLine($"Horno encencido, Tª de la sala: {Temperatura} grados C");
    }

    override public string ToString()
    {
        return $"P {base.ToString()}";
    }
}
```

Vamos a probar que todo funcione correctamente

```csharp
var panadero = new Panadero(40f, 2500f, "Pablo", 27);

Console.WriteLine(panadero); // P Pablo
panadero.Trabajar(); // Horno encencido, Tª de la sala: 40 grados C
panadero.CobrarPagaExtra(); // Este mes paga extra: 5000 euretes
```

Y por supuesto ahora podemos interactuar entre objetos, por ejemplo, hagamos que un cliente pueda comprar carne, actualizaremos la clase *Cliente*

```csharp
class Cliente(
    float dinero = 500f,
    string nombre = "Anónimo",
    int edad = -1
) : Persona(nombre, edad)
{
    public float Dinero { get; set; } = dinero;

    public void Comprar(float precio)
    {
        if (precio > Dinero)
        {
            Console.WriteLine($"Saldo ({Dinero}) insuficiente para comprar el producto que cuesta {precio} euros");
        } else {
            Dinero -= precio;
            Console.WriteLine($"{this}, te quedan {Dinero} euros. El articulo costaba: {precio} euros");
        }
    }

    public void Ingresar(float cantidad)
    {
        Dinero += cantidad;
        Console.WriteLine($"Has ingresado {cantidad} euros. Ahora tienes en total {Dinero} euros");
    }

    public void ComprarCarne(Carnicero carnicero, int filetes)
    {
        carnicero.Trabajar();
        Console.WriteLine($"Gracias por los {filetes} filetes, {carnicero.Nombre}");
        Console.WriteLine($"De nada, {Nombre}");
    }

    override public string ToString()
    {
        return $"C {base.ToString()}"; // Ponemos C y el ToString de la clase padre para diferenciar que la persona es un Cliente
    }
}
```

```csharp
var carnicero = new Carnicero(nombre:"Paco");
var cliente = new Cliente(nombre:"Pablo");

cliente.ComprarCarne(carnicero, 5);
```