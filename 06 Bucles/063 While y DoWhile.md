# `While` y  `Do while`

Los bucles `while` y `dowhile` te permiten ejecutar un bloque de código mientras se cumpla una condición. Estas estructuras de control es perfecta cuando no sabes el número de veces que tienes que repetir un bloque de código

## Sintaxis de `while`

La sintaxis de `while` es la siguiente:

- Escribe la palabra reservada while => `while`
- Pon apertura y cierre de paréntesis `()`  => `while ()`
- Seguido de bloque de código  => `while () {}`
- Escribe dentro del paréntesis la condición que se tiene que cumplir para **continuar ejecutando** el bloque de código
- Implementa las sentencias que se tienen que repetir en cada iteración
- **IMPORTANTE**: no te olvides de actualizar la condición en cada iteración porque si no estaríamos dentro de un bucle infinito y probablemente tenga un desbordamiento de pila *stack overflow*

```csharp
int random = 0;
int intentos = 0;
List<int> randomsObtenidos = [];

// Este bucle se ejecuta mientras random sea distinto de 1
// En el momento en el que el random sea 1, para de repetirse el bloque de código del while
while (random != 1)
{
    Random rnd = new();
    random = rnd.Next(1, 11);  // Random entre 1 y 10

    randomsObtenidos.Add(random);
    intentos++;
}

Console.WriteLine($"Intentos hasta conseguir el 1: {intentos}\nNúmeros random calculados: {string.Join(", ", randomsObtenidos)}");
```

## Sintaxis de `do while`

La sintaxis de `do while` es la siguiente:

- Escribe la palabra reservada do => `do`
- Pon apertura y cierre de bloque de código `{}`  => `do {}`
- Seguido de bloque la palabra reservada while, paréntesis y condición  => `do {} while (condicion);`
- Implementa las sentencias que se tienen que repetir en cada iteración
- No te olvides de actualizar la condición en cada iteración porque si no estaríamos dentro de un bucle infinito y probablemente tenga un desbordamiento de pila *stack overflow*

Este bucle es bastante parecido al `while` pero con una diferencia, el bloque de código se ejecuta, mínimo, una vez y luego se evalúa la condición, mientras que en el bucle `while` la condición se evalúa antes de ejecutarse el bloque de código por lo que puede ser que dicho bloque de código nunca llegue a ejecutarse

```csharp
int random = 0;
int intentos = 0;
List<int> randomsObtenidos = [];

do
{
    Random rnd = new();
    random = rnd.Next(1, 11);  // Random entre 1 y 10

    randomsObtenidos.Add(random);
    intentos++;
} while (random != 1);
// Este bucle se ejecuta mientras random sea distinto de 1
// En el momento en el que el random sea 1, para de repetirse el bloque de código del while

Console.WriteLine($"Intentos hasta conseguir el 1: {intentos}\nNúmeros random calculados: {string.Join(", ", randomsObtenidos)}");
```