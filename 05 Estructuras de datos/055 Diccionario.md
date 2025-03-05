# Diccionario

Un diccionario es una estructura de datos en la que cada item es un par de **clave-valor**. Es útil para manejar datos que necesitan ser accedidos rápidamente mediante una clave única

## Sintaxis de los diccionarios

```csharp
// Inicialización
Dictionary<string, int> puntuaciones = new()
{
    { "Pablo", 5 },
    { "Elisabeth", 10 },
    { "Isabella", 8 },
};
// Inicialización simplificada
Dictionary<string, int> puntuacionesSimplificada = new()
{
    { "Pablo", 5 },
    { "Elisabeth", 10 },
};
```

## Operaciones CRUD en un diccionario

CRUD es un acrónimo que representa las cuatro operaciones básicas que se pueden realizar en una base de datos o una estructura de datos:

- **C**reate (crear)
- **R**ead (leer)
- **U**pdate (actualizar)
- **D**elete (borrar)
 
A continuación, vas a aprender cómo aplicar cada una de estas operaciones en un diccionario
 
```csharp
Dictionary<string, int> puntuaciones = new()
{
    { "Pablo", 5 },
    { "Elisabeth", 10 },
    { "Isabella", 8 },
};
string clave = "Pablo";
int puntos = puntuaciones[clave];

// CREATE
puntuaciones.Add("Isabella", 10);

// READ
Console.WriteLine($"{clave} tiene {puntos} puntos"); // Pablo tiene 5 puntos

// UPDATE
++puntuaciones[clave]; // Añadimos un punto a Pablo

// DELETE
puntuaciones.Remove(clave);

// Existencia de una clave
puntuaciones.ContainsKey(clave); // False (la borramos antes)
```