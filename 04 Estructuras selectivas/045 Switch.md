# Sentencia `switch` en C#

La sentencia `switch` es una estructura de control que permite ejecutar diferentes bloques de código basados en el valor de una expresión. Es una alternativa a las sentencias `if-else if` cuando se necesita evaluar una sola expresión contra múltiples valores posibles

## Sintaxis de `switch`

La sintaxis básica de una sentencia `switch` en C# es la siguiente:

- Usamos la palabra reservada `switch`
- Seguida de paréntesis `()`
- Dentro de los paréntesis la expresión a evaluar
- Abrimos y cerramos bloque de código `{}`
- Dentro del bloque de código ponemos la palabra reservada `case`
- Detrás de `case` el valor al que comparar la expresión y `:`
- En la siguiente línea, el bloque de código que ha de ejecutarse en caso de que el valor de la expresión anterior sea igual al valor del `case`
- La palabra reservada `break` para que no siga ejecutando las líneas posteriores del `switch`
- Repetimos los 4 pasos anteriores tantas veces como casos queramos controlar
- Por último, si queremos controlar la opción de que la expresión no sea ninguno de los valores, haremos uso de la palabra reservada `default` seguida de `:`

```csharp
switch (expresion) {
    case valor1:
        // Bloque de código que se ejecuta si la expresión es igual a valor1
        break;
    case valor2:
        // Bloque de código que se ejecuta si la expresión es igual a valor2
        break;
    case valor3:
        // Bloque de código que se ejecuta si la expresión es igual a valor3
        break;
    // Podrías tener tantos casos como necesites
    default:
        // Bloque de código que se ejecuta si la expresión no coincide con ningún valor
        break;
}
```

Veamos con un ejemplo real

```csharp
int dia = 3;

switch (dia) {
    case 1:
        Console.WriteLine("Lunes");
        break;
    case 2:
        Console.WriteLine("Martes");
        break;
    case 3:
        Console.WriteLine("Miércoles");
        break;
    case 4:
        Console.WriteLine("Jueves");
        break;
    case 5:
        Console.WriteLine("Viernes");
        break;
    case 6:
        Console.WriteLine("Sábado");
        break;
    case 7:
        Console.WriteLine("Domingo");
        break;
    default:
        Console.WriteLine("Día no válido");
        break;
}
```

En este caso, la expresión a comparar es un número, pero podemos comparar por ejemplo `strings`

```csharp
string fruta = "manzana";

switch (fruta) {
    case "manzana":
        Console.WriteLine("La fruta es una manzana.");
        break;
    case "banana":
        Console.WriteLine("La fruta es una banana.");
        break;
    case "naranja":
        Console.WriteLine("La fruta es una naranja.");
        break;
    default:
        Console.WriteLine("Fruta no reconocida.");
        break;
}
```

A diferencia de las sentecias `if-else-if` y demás, como hemos visto el `switch` se usa en caso de que necesitemos evaluar una **sola expresión**, mientras que con las sentencias `if-else-if` podemos evaluar **expresiones distintas**