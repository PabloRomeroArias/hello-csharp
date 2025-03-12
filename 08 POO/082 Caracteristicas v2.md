# Características v2 de la POO

En esta segunda versión de este módulo vamos a aplicar algunas de las características que hemos visto en el apartado de [teoría](080%20Teoria.md)

Supongamos que un mecánico nos contrata para una aplicación modesta en la que tenemos que gestionar el arreglo de bicicletas. Necesita que almacenemos el número de ruedas y el color de la bicicleta. En el taller podremos llenar las ruedas, pintar la bicicleta y ajustar el sillín

El taller va sobre ruedas y ahora también admite motos, cuyos datos importantes son el color y el número de ruedas. Se podrán pintar las motos, ajustar el manillar y llenar las ruedas

¡Estamos de celebración! El taller sigue creciendo y por consecuencia la app, ahora el taller también admite coches. Necesitamos almacenar el número de ruedas y de puertas y el color. Se podrá pintar el coche, llenar las ruedas y reparar las puertas

Nosotros, que desde el principio nos adelantamos a los acontecimientos, sabíamos que esto iba a escalar, por lo que antes de picar estuvimos analizando cuál era la mejor manera de hacer que esto escale, y es mediante **interfaces**

Cuando escuchemos la palabra **interfaz**, se nos tiene que venir a la mente la palabra **contrato**. En un contrato, queda claro todas las funciones mínimas que hay que tener

En nuestro caso, sabemos que en un taller entran vehiculos, la mayoria de vehiculos tendran como ya sabemos algunos atributos y metodos comunes:

- Atributos comunes
  - Número de ruedas
  - Color
- Métodos comunes
  - Pintar vehículo
  - Llenar las ruedas

Una vez definida la interfaz, ¡vamos a picar!

```csharp
// El nombre de la interfaz va precedido por una I mayúscula
interface IVehiculo
{
    int Ruedas { get; set; }
    string Color { get; set; }

    void Pintar(string color);
    void LlenarRuedas();
}
```

Ahora, vamos a **firmar el contrato** con cada uno de los vehículos, es decir, vamos a **implementar** la *interfaz*

```csharp
class Bicicleta(
    int ruedas = 1,
    string color = "azul"
) : IVehiculo
{
    public int Ruedas { get; set; } = ruedas;
    public string Color { get; set; } = color;

    public void Pintar(string color)
    {
        Color = ""; // Primero quitamos el color que ya tenía para no hacer capas
        Color = color; // Luego pintamos
    }

    public void LlenarRuedas()
    {
        if (Ruedas == 1)
            Console.WriteLine("Rueda del monociclo llena");
        else
            Console.WriteLine($"Las {Ruedas} ruedas de la bicicleta están llenas");
    }

    public void AjustarSillin()
    {
        Console.WriteLine("Sillín ajustado correctamente");
    }
}
```

```csharp
class Moto(int ruedas = 2, string color = "blanco") : IVehiculo
{
    public int Ruedas { get; set; } = ruedas;
    public string Color { get; set; } = color;

    public void Pintar(string color)
    {
        Color = ""; // Primero quitamos el color que ya tenía para no hacer capas
        Color = color; // Luego pintamos
    }

    public void LlenarRuedas()
    {
        Console.WriteLine($"Las {Ruedas} ruedas de la moto están llenas");
    }
}
```

```csharp
class Coche(
    int ruedas = 4,
    string color = "blanco",
    int puertas = 5
) : IVehiculo
{
    public int Ruedas { get; set; } = ruedas;
    public string Color { get; set; } = color;
    public int Puertas { get; set; } = puertas;

    public void Pintar(string color)
    {
        Color = ""; // Primero quitamos el color que ya tenía para no hacer capas
        Color = color; // Luego pintamos
    }

    public void LlenarRuedas()
    {
        Console.WriteLine($"Las {Ruedas} ruedas del coche están llenas");
    }

    public void RepararPuertas()
    {
        Console.WriteLine($"Las {Puertas} puetas han sido reparadas");
    }
}
```