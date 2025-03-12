# ForEach

El método `forEach` te permite recorrer todos y cada uno de los items de una estructura de datos:

## Sintaxis de `foreach`

A continuación puedes ver cómo se pueden recorrer las siguiente estructuras de datos:

```csharp

// ForEach en strings
string frase = "Esta frase va a ser recorrida por un foreach";

// Cada elemento de un string es un caracter
foreach(char caracter in frase) // Podemos ponerle el nombre que queramos, pero ya sabemos que cuanto más descriptivo el nombre, mejor para nuestro yo del futuro
{
    Console.Write($"{caracter}-");
}

// ForEach en arrays
string[] frutas = [ "Pera", "Plátano", "Manzana", "Melón", "Sandía", "Fresa", "Melocotón" ];

foreach(string fruta in frutas)
{
    Console.Write($"Fruta iterada: {fruta}");
}

// ForEach en matrices
string[][] salaCine = [
    ["A1", "A2", "A3"],
    ["B1", "B2", "B3"],
    ["B1", "A2", "B3"],
];

foreach(string[] fila in salaCine)
{
    // Recuerda que cada elemento de la matriz es una fila, por lo que necesitamos un bucle anidado
    foreach(string butaca in fila)
    {
        Console.Write($"Butaca {butaca} | ");
    }
}

// ForEach en diccionarios
Dictionary<string, int> puntuaciones = new()
{
    { "Pablo", 5 },
    { "Elisabeth", 10 },
    { "Isabella", 8 },
};

foreach(KeyValuePair<string, int> puntuacion in puntuaciones)
{
    Console.WriteLine($"{puntuacion.Key} tiene {puntuacion.Value} puntos");
}
```