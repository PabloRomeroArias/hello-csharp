# Sentencia `if-else` en C#

La sentencia `if-else` es una estructura de control que permite ejecutar diferentes bloques de código en función de si una condición es verdadera o falsa. Es una de las estructuras más básicas y fundamentales en la programación, utilizada para tomar decisiones en el flujo del programa

## Sintaxis de `if-else`

La sintaxis básica de una sentencia `if-else` en C# es la siguiente:

- Aplicamos la sintaxis de la sentencia selectiva `if`
- Fuera del bloque de código del `if`, usamos la palabra reservada `else`
- Abrimos y cerramos bloque de código
- Escribimos dentro del bloque de código del `else` las sentencias que queremos que se ejecuten en caso de que **NO** se cumpla la condición

```csharp
if (condición)
{
    // Bloque de código que se ejecuta si la condición es verdadera
}
else
{
    // Bloque de código que se ejecuta si la condición es falsa
}
```

Aquí tienes un ejemplo real

```csharp
int edad = 16;

Console.WriteLine("SIEMPRE me ejecuto, ANTES de la sentencia if-else");

if (edad >= 18)
{
    Console.WriteLine("Eres mayor de edad.");
}
else
{
    Console.WriteLine("Eres menor de edad.");
}

Console.WriteLine("SIEMPRE me ejecuto, DESPUÉS de la sentencia if-else");
```

## Operador ternario

El *operador ternario* o *operador elvis* es un operador que te facilita el uso de conficionales. El segundo nombre lo recibe porque `?:` parece el famoso tupé del cantante de rock *Elvis Presley*

Para hacer uso de este operador, necesitas una condición, la consecuencia de que se cumpla la condición y la alternativa en caso de que no se cumpla la condición. Paso a paso, sería:

- Condición
- Signo `?`
- Consecuencia de ser positiva la condición
- Signo `:`
- Alternativa si no se cumple la condición

Aquí tienes un ejemplo real

```csharp
int edad = 16;

string mensaje = edad >= 18 ? "Es mayor de edad" : "Es MENOR de edad";
Console.WriteLine(mensaje);
```