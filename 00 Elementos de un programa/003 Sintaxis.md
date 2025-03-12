# Sintaxis

| Nombre                | Símbolo            | Descripción                                                                |
|-----------------------|--------------------|----------------------------------------------------------------------------|
| Fin de sentencia      | `;`                | Al final de cada sentencia (se recomienda nueva línea tras usar `;`         |
| Comentario de línea   | `//`               | Un comentario de una sola línea. Aclara o explica brevemente el código     |
| Comentario multilínea | `/* comentario */` | Un comentario que puede abarcar múltiples líneas. Explicaciones extensas   |
| Bloque de código      | `{ sentencias }`   | Agrupa sentencias entre llaves `{}`. Puede ejecutarse o no lo que contiene |

### Fin de sentencia
```csharp
string nombre = "Pablo"; // Al final, se pone el ;
nombre = "Elisabeth"; Console.WriteLine(nombre); // Se pueden poner setencias una detrás de otra, pero se recomienda no hacer esto y usar una nueva línea para mejor legibilidad
```

### Comentario de línea

```csharp
// Esto es un comentario de una sola línea y no se va a tener en cuenta a la hora de ejecutar el script
string nombre = "Pablo";
Console.WriteLine(nombre);
// nombre = "Pepe";
// Console.WriteLine(nombre); Si lo ponemos al principio, no se tendrá en cuenta aún habiendo escrito código de TypeScript
```

### Comentario multilínea

```csharp
/*
Esto es un comentario
de múltiples líneas.
Se puede usar para descripciones largas
o para desactivar bloques de código extensos.
*/
```

### Bloque de código

```csharp
int edad = 30;
string mensaje;
// Aquí hay dos bloques de código
if (edad >= 18) { // Primer bloque de código
    mensaje = "Eres mayor de edad";
} else { // Segundo bloque de código (ESTE NO SE EJECUTA)
    mensaje = "Eres menor de edad";
}
```