# Sentencia `if-else` Anidados en C#

La sentencia `if-else` *anidada* permite evaluar múltiples condiciones de manera jerárquica. Esto significa que puedes tener sentencias `if-else` dentro de otra sentencia `if-else`, ya sea dentro del bloque de códgio del `if` o del bloque de código del `else`. Esta técnica es útil cuando necesitas tomar decisiones más complejas que dependen de varias condiciones

## Sintaxis de `if-else` Anidados

La sintaxis básica de una sentencia `if-else` anidada es la siguiente:
- Aplicamos

```csharp
if (condicion1) {
    // Bloque de código que se ejecuta si la condición1 es verdadera
    if (condicion2) {
        // Bloque de código que se ejecuta si la condición2 es verdadera
        if (condicion3) {
            // Bloque de código que se ejecuta si la condición3 es verdadera
        } else {
            // Bloque de código que se ejecuta si la condición3 es falsa
        }
    } else {
        // Bloque de código que se ejecuta si la condición2 es falsa
    }
} else {
    if (condicion4) {
        // Bloque de código que se ejecuta si la condición4 es verdadera
    } else {
        // Bloque de código que se ejecuta si la condición4 es falsa
    }
```

Veamos con un ejemplo real

```csharp
int edad = 25;
bool tieneLicencia = true;
bool noHaBebidoAlcohol = true;

if (edad >= 18) {
    if (tieneLicencia) {
        if (noHaBebidoAlcohol) {
            Console.WriteLine("Puedes conducir");
        } else {
            Console.WriteLine("No puedes conducir porque has bebido alcohol");
        }
    } else {
        Console.WriteLine("Necesitas una licencia para conducir");
    }
} else {
    Console.WriteLine("Es menor de edad"); // Recuerda que estás dentro de un bloque de código, puedes ejecutar la sentencia que necesites
    if (edad == 17) {
        Console.WriteLine("Ya te queda poco");
    } else {
        Console.WriteLine("Aún te quedan unos añitos");
    }
}
```

Las sentencias if-else anidadas son útiles para manejar decisiones complejas que dependen de múltiples condiciones. Sin embargo, es importante mantener el código claro y legible, evitando anidar demasiados niveles de condiciones
