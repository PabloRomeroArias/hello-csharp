# Tupla

Una tupla es un array en la que se define cuántos elementos tiene y el tipo de dato de cada item

## Sintaxis de las *tuplas*

Supongamos que queremos almacenar el nombre, puntuación y edad de una persona, es decir, un `string` y dos `int`

```csharp
// Inicialización
Tuple<string, int, int> tupla = new Tuple<string, int, int>("Pablo", 5, 27);
// Inicialización simplificada
Tuple<string, int, int> tupla = new("Pablo", 5, 27);
```

## Operaciones CRUD en una *tupla*

```csharp
Tuple<string, int, int> tupla = new("Pablo", 5, 27);

// Create NO PODEMOS CREAR ELEMENTOS

// Read
Console.WriteLine(tupla.Item1) // Nombre de la persona
Console.WriteLine(tupla.Item2) // Puntuación de la persona
Console.WriteLine(tupla.Item3) // Edad de la persona

// Update NO PODEMOS ACTUALIZAR ELEMENTOS

// Delete NO PODEMOS BORRAR ELEMENTOS
```