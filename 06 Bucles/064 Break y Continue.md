# Break y Continue

**Break** es una palabra reservada cuya sentencia se usa para saltar y salir de un bloque de código. Ya lo has visto anteriormente el la estructura selectiva `switch`. Pero también lo puedes usar en los bucles como veremos a continuación

Por otro lado, **Continue** es una palabra cuya sentencia se usa para saltarse las siguientes líneas de código y pasar a la siguiente iteración

Puedes hacer uso de estas dos sentencias en cualquier bucle, vas a ver un ejemplo en el bucle `for`

```csharp
// Uso de BREAK en for
for (int i = 0; i <= 10; i++)
{
    if (i == 5)
    {
        // Cuando i sea 5, no se imprimirán más números
        break;
    }
    Console.WriteLine($"Iteración: {i}");
}

// Uso de CONTINUE en for
for (int i = 0; i <= 10; i++)
{
    Console.WriteLine($"¿Me ejecuto en todas las iteraciones?: {i}");
    if (i == 5)
    {
        // Cuando i sea 5, pasa a la siguiente iteración sin ejecutar las próximas líneas de código
        continue;
    }
    Console.WriteLine($"¿Y yo?: {i}");
}
```