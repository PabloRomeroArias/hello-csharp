# Formateo de strings

Cuando queramos dar formato a un *string* podemos hacer uso de las plantillas de literales. De esta manera, podemos crear un mensaje de una manera más sencilla cuando queramos mostrar datos, como se muestra en el siguiente ejemplo:

```csharp
string nombre = "Pablo";
int edad = 27;
string mensaje = $"Hola ${nombre}, tienes ${edad} años."; // IMPORTANTE: la cadena de texto tiene que estar entre un ` de apertura y otro ` de cierre

Console.WriteLine(mensaje); // Hola Pablo, tienes 27 años
```
