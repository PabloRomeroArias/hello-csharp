# Matrices

Una matriz es una estructura de datos lineal bidimensional que permite almacenar una colección de colecciones de elementos **del mismo tipo** en una sola variable

Las matrices son útiles para manejar datos y realizar operaciones entre ellos de manera sencilla y eficiente

Cada elemento de la matriz está ordenado en filas y columnas, y a cada uno le corresponde un **índice doble**, uno para la fila y otro para la columna, empezando ambos por el 0 y llegando hasta `M - 1` las filas y `N - 1` las columnas siendo `N` el número de filas que hay y `M` el número de columnas

## Sintaxis de las matricess

Puedes declarar matrices de varias maneras, ya sea un array de arrays o una lista de listas. Recuerda que los arrays son menos editables que las listas, tú como programador tienes que tener claro qué tipo de dato usar en cada momento

```csharp
// Matriz como array de arrays
int[][] arrayDeArrays = [
    [1, 2, 3], 
    [4, 5, 6],
    [7, 8, 9]
];
// Matriz como lista de listas
List<List<int>> listaDeListas = [
    [1, 2, 3], 
    [4, 5, 6],
    [7, 8, 9]
];
// Matriz como lista de arrays
static void Main(string[] args)
{
    List<int[]> listaDeArrays = [
        [1, 2, 3], 
        [4, 5, 6],
        [7, 8, 9]
    ];
}
```

## Operaciones CRUD en una matriz

CRUD es un acrónimo que representa las cuatro operaciones básicas que se pueden realizar en una base de datos o una estructura de datos:

- **C**reate (crear)
- **R**ead (leer)
- **U**pdate (actualizar)
- **D**elete (borrar)
 
Recuerda que cada item de la matriz es otra estructura de datos, por lo que las operaciones **CRUD** serán las mismas que puedas realizar con la estructura de datos en sí

Vamos a usar lista de listas para poder hacer todas las operaciones **CRUD**

```csharp
List<List<string>> salaDeCine = [
    ["A1", "A2", "A3"], 
    ["B1", "B2", "B3"],
    ["C1", "C2", "C3"]
];

// CREATE
salaDeCine.Add(["D1", "D2", "D3"]);

// READ
Console.WriteLine($"Butaca: {salaDeCine[3][0]}"); // Butaca: D1
Console.WriteLine($"Butaca: {salaDeCine[3][1]}"); // Butaca: D2
Console.WriteLine($"Butaca: {salaDeCine[3][2]}"); // Butaca: D3

// UPDATE
salaDeCine[3][0] = "W1"; // Actualizamos
Console.WriteLine($"Butaca actualizada: {salaDeCine[3][0]}");

// DELETE
salaDeCine.RemoveAt(3); // Borramos

Console.WriteLine($"Butaca: {salaDeCine[3][0]}"); // ERROR
```