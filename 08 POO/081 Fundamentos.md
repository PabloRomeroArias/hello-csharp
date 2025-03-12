# Fundamentos de la POO

En este apartado, vamos a ir trabajando, construyendo y actualizando para aprender los conceptos que hemos visto en la [teoría](080%20Teoria.md) de la Programación Orientada a Objetos

Para ello, vamos a usar la clase *Persona* y añadiendo cada vez más complejidad para que veamos la potencia que tiene este paradigma de programación. Sobre todo para el mundo de las aplicaciones, ya que un cliente final va a interactuar con interfaces fáciles de usar, debido a que él no es un experto informático

## Nuestra primera clase

vamos a crear nuestra primera clase, en este caso *Persona*. Es buena práctica que cada clase tenga su propio archivo. Y también se recomienda crear una carpeta en la que estén todos los modelos de datos

```csharp
class Persona {}
```

Como hemos dicho, una clase no es más que una plantilla, ahora vamos a **instanciar** un objeto de tipo persona, ¿se te ocurre cómo?

```csharp
// Hemos instanciado un objeto de tipo persona, almacenado en la variable p
Persona p = new Persona();
Console.WriteLine(p);
```

## Atributos

Recuerda que los atributos son propiedades que tiene una clase. En este caso, una persona puede tener *nombre* y *edad*, por ejemplo

```csharp
class Persona {
    public string Nombre = "Invitado";
    public int Edad = -1;
}
```

Y ahora ya puedes acceder a esos atributos de la clase

```csharp
var p = new Persona();
Console.WriteLine(p.Nombre); // Invitado
Console.WriteLine(p.Edad); // -1
```

O incluso actualizarlos

```csharp
var p = new Persona();
Console.WriteLine(p.Nombre); // Invitado
Console.WriteLine(p.Edad); // -1

p.Nombre = "Pablo";
p.Edad = 27;

Console.WriteLine(p.Nombre); // Pablo
Console.WriteLine(p.Edad); // 27
```

Esto que hemos hecho es una mala práctica en **C#** ya que no se debe acceder a los atributos directamente. Para que puedas acceder a ellos, ya sea para asignar un nuevo valor o para leer, debes de hacer uso de **get** and **set** en cada atributo. De esta manera, no accederás directamente a ellos, sino que leerás con **get** y asignarás con **set**

```csharp
class Persona {
    public string Nombre { get; set; }
    public int Edad { get; set; }
}
```

De esta manera ahora sí que estás haciendo uso de buenas prácticas en **C#**

```csharp
var p = new Persona();
p.Nombre = "Pablo";
p.Edad = 27;

Console.WriteLine(p.Nombre); // Pablo
Console.WriteLine(p.Edad); // 27
```

## Constructor

Para que puedas instanciar un objeto a la vez que asignas valor a sus atributos, tienes que crear métodos **constructor**. Para que un método sea *constructor*, lo tienes que llamar de igual manera que la clase

```csharp
class Persona {
    public string Nombre { get; set; } = "Invitado";
    public int Edad { get; set; } = -1;

    public Persona()
    {
        Nombre = "Pablo";
        Edad = 27;
    }
}
```

Ahora, cada vez que instancies un objeto de tipo persona, tendrá esos atributos

```csharp
var p1 = new Persona();
var p2 = new Persona();

Console.WriteLine(p1.Nombre); // Pablo
Console.WriteLine(p2.Nombre); // Pablo
```

Puedes crear tantos constructores como quieras

```csharp
class Persona {
    public string Nombre { get; set; } = "Invitado";
    public int Edad { get; set; } = -1;

    public Persona(string nombre)
    {
        Nombre = nombre;
    }

    public Persona(int edad)
    {
        Nombre = "Invitado";
        Edad = edad;
    }

    public Persona(string nombre, int edad)
    {
        Nombre = nombre;
        Edad = edad;
    }
}
```

Y para instanciar un objeto con cada constructor, tienes que llamar a cada método constructor que te interese

```csharp
var p1 = new Persona();
var p2 = new Persona("Elisabeth");
var p3 = new Persona(10);
var p4 = new Persona("Isabella", 25);
```

También puedes restringir la manera en que se pueda instanciar una persona, si por ejemplo quieres obligar a que meta tanto nombre como edad, usando el constructor primario

```csharp
class Persona(string nombre, int edad) {

    public string Nombre { get; set; } = nombre;
    public int Edad { get; set; } = edad;
}
```

O combinar valores con el constructor primario con variables opcionales para hacerlo más sencillo

```csharp
class Persona(string nombre = "Invitado", int edad = -1)
{
    public string Nombre { get; set; } = nombre;
    public int Edad { get; set; } = edad;
}
```

```csharp
var p1 = new Persona();
var p2 = new Persona("Elisabeth");
var p3 = new Persona(edad:10); // Si no referenciamos el parámetro edad:, nos da error ya que el primer argumento debe ser string (nombre)
var p4 = new Persona("Isabella", 25);

Console.WriteLine($"{p1.Nombre}, {p1.Edad} años"); // Invitado, -1 años
Console.WriteLine($"{p2.Nombre}, {p2.Edad} años"); // Elisabeth, -1 años
Console.WriteLine($"{p3.Nombre}, {p3.Edad} años"); // Invitado, 10 años
Console.WriteLine($"{p4.Nombre}, {p4.Edad} años"); // Isabella, 25 años
```

## Método

Para que puedas crear un método de una clase, escribe una función dentro del bloque de código de la clase. Por ejemplo, vamos a crear un método de persona que devuelva su nombre y edad. Cabe destacar que la propia clase ya conoce sus propiedades, por lo que no se necesitaría pasar como argumento ninguna variable

```csharp
class Persona(string nombre = "Invitado", int edad = -1)
{
    public string Nombre { get; set; } = nombre;
    public int Edad { get; set; } = edad;

    // Escribimos el método DatosPersona
    public string DatosPersona()
    {
        return $"{Nombre}, {Edad} años"; // Isabella 25
    }
}
```

De esta manera, ahora un objeto de tipo persona puede escribir por consola su nombre y edad por el mero hecho de ser *Persona*

```csharp
var p1 = new Persona();
var p2 = new Persona("Elisabeth");
var p3 = new Persona(edad:10);
var p4 = new Persona("Isabella", 25);

Console.WriteLine(p1.DatosPersona()); // Invitado, -1 años
Console.WriteLine(p2.DatosPersona()); // // Elisabeth, -1 años
Console.WriteLine(p3.DatosPersona()); // Invitado, 10 años
Console.WriteLine(p4.DatosPersona()); // Isabella, 25 años
```

Si pensamos en otro tipo de dato, cuando mostramos por pantalla, no tenemos que llamar a ningún método, sino que escribimos el nombre de la variable y esta se encarga de imprimirse sola, ¿cómo podemos conseguir esto?

Como ya sabes, **C#** es orientado a objetos, por lo que ya existe una jerarquía de clases predefinida por el propio lenguaje. Esto quiere decir que ya existen métodos predefinidos que podemos usar a nuestro favor. Uno de los métodos más importantes es el método `ToString`, que se encarga de devolver un `string` con los atributos formateados de manera amigable

```csharp
class Persona(string nombre = "Invitado", int edad = -1)
{
    public string Nombre { get; set; } = nombre;
    public int Edad { get; set; } = edad;

    // Sobreescribimos el método ToString
    override public string ToString()
    {
        return $"{Nombre}, {Edad} años"
    }
}
```

De esta manera, ya no necesitamos llamar a ningún método, siempre que se imprima por pantalla o se formate un string, se llamará automáticamente a este método

```csharp
var p = new Persona("Pablo", 27);

var mensaje = $"Persona con formateo de string: {p}";
Console.WriteLine(mensaje);

Console.Write("Persona llamando a console.writeline: ");
Console.WriteLine(p);
```

También podemos pasar argumentos a los métodos

```csharp
class Persona(string nombre = "Invitado", int edad = -1)
{
    public string Nombre { get; set; } = nombre;
    public int Edad { get; set; } = edad;

    public void SaludarA(Persona otro)
    {
        Console.WriteLine($"Hola {otro.Nombre}, me llamo {Nombre}");
    }

    override public string ToString()
    {
        return $"{Nombre}, {Edad} años";
    }
}
```

Y ahora ya puedes realizar la acción de que una persona salude a otra

```csharp
var pablo = new Persona("Pablo", 27);
var elisabeth = new Persona("Elisabeth", 20);

// objeto pablo saluda a objeto elisabeth
pablo.SaludarA(elisabeth); // Hola Elisabeth, me llamo Pablo
```