# Array y lista

Un array y una lista son dos estructuras de datos que permiten almacenar una colección de *elementos* **del mismo tipo** en una sola variable de manera ordenada

Los Arrays y las listas son probablemente la estructura de datos más importante. Son útiles para manejar colecciones de datos y realizar operaciones entre ellos de manera sencilla y más o menos eficiente

Cada *elemento* de la lista también se suele denominar *item*. Estos están ordenados y a cada uno le corresponde un *índice*, empezando por el 0 y yendo hasta `N - 1`, siendo `N` el número de elementos que hay

## Sintaxis de los `array`s
Para declarar el tipo del array tenemos que añadir, a parte del tipo de cada elemento, apertura y cierre de corchetes para indicar que será un array del tipo indicado

En la declaración de los arrays, tenemos que indicar o bien el tamaño del array o directamente los elementos que contendrá el array

Se pueden declarar arrays de varias maneras

```csharp
// MANERA 1
string[] arrayConTamanio = new string[2]; // 2 es el tamaño del array. Array de strings. Dos elementos (índices 0 y 1)
arrayConTamanio[0] = "Hola"; // Y asignamos valor a los índices
arrayConTamanio[1] = "Mundo"; // Que necesitemos
arrayConTamanio[2] = "Esto da error: System.IndexOutOfRangeException"; // ERROR, índice 3 no corresponde a un ítem del array
// MANERA 2 y simplificaciones. Inicialización mediante elementos
string[] arrayConItems = new string[] { "Hola", "Mundo" };
string[] arrayConItemsSimplificado1 = new[] { "Hola", "Mundo" };
string[] arrayConItemsSimplificado2 = { "Hola" , "Mundo" };
// MANERA 3 Esta es la recomendada
string[] array = [ "Hola", "Mundo" ]; // creates populated array of length 2
```

## Operaciones CRUD en un `Array`

CRUD es un acrónimo que representa las cuatro operaciones básicas que se pueden realizar en una base de datos o una estructura de datos:

- **C**reate (crear)
- **R**ead (leer)
- **U**pdate (actualizar)
- **D**elete (borrar)
 
A continuación, vas a aprender cómo aplicar cada una de estas operaciones en un array
 
```csharp
string[] coches = ["BMW", "Audi", "Ferrari"];

// CREATE
// No se puede añadir elementos en un array

// READ
string coche = coches[0]; // BMW
coche = coches[1]; // Audi
coche = coches[2]; // Ferrari
coche = coches[3]; // ERROR

// UPDATE
coches[0] = "Porsche";

// DELETE
// No se puede eliminar elementos en un array
```

## Sintaxis de las listas
Para declarar listas podemos

```csharp
// Inicialización
List<string> lista = new List<string> { "Hola", "Mundo" };
// Inicialización simplificada
List<string> listaSimplificada = [ "Hola", "Mundo" ];
```

## Operaciones CRUD en una lista

CRUD es un acrónimo que representa las cuatro operaciones básicas que se pueden realizar en una base de datos o una estructura de datos:

- **C**reate (crear)
- **R**ead (leer)
- **U**pdate (actualizar)
- **D**elete (borrar)
 
A continuación, vas a aprender cómo aplicar cada una de estas operaciones en una lista

```csharp
List<string> coches = ["BMW", "Audi", "Ferrari"];

// CREATE
coches.Add("Porsche");

// READ
string coche = coches[0]; // BMW

// UPDATE
coches[0] = "Mercedes";

// DELETE
coches.RemoveAt(0); // Borramos el índice 0
coches.Remove("Audi"); // Borramos el elemento "Audi"
```