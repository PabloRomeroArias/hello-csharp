# Métodos de String

Las cadenas de texto (strings) son una parte fundamental de la programación. En **C#**, los strings vienen con una variedad de métodos incorporados que permiten realizar operaciones comunes, como la manipulación y el análisis de texto. Estos métodos facilitan tareas como la búsqueda de subcadenas, la conversión de mayúsculas a minúsculas, la división de cadenas en partes más pequeñas, y mucho más.

### Métodos comunes de string

```csharp
string texto = "Hola Mundo";

// Length -> longitud del string
Console.WriteLine(texto.Length); // 10

// ToUpper() -> convierte a mayúsculas
Console.WriteLine(texto.ToUpper()); // "HOLA MUNDO"

// ToLower() -> convierte a minúsculas
Console.WriteLine(texto.ToLower()); // "hola mundo"

// CharAt() -> carácter en una posición específica
Console.WriteLine(texto[0]); // 'H'
Console.WriteLine(texto[5]); // 'M'

// IndexOf() -> posición de la primera aparición
Console.WriteLine(texto.IndexOf("Mundo")); // 5
Console.WriteLine(texto.IndexOf("Adiós")); // -1

// Substring() -> parte de la cadena entre dos índices
Console.WriteLine(texto.Substring(0, 4)); // "Hola"
Console.WriteLine(texto.Substring(5)); // "Mundo"

// Replace() -> reemplaza una subcadena
string nuevoTexto = texto.Replace("Mundo", "CSharp");
Console.WriteLine(nuevoTexto); // "Hola CSharp"

// Split() -> divide la cadena en un array
string frutasTexto = "manzana,banana,cereza";
string[] frutas = frutasTexto.Split(',');
Console.WriteLine(string.Join(", ", frutas)); // "manzana, banana, cereza"

// Trim() -> elimina espacios en blanco de ambos extremos
string textoConEspacios = "   Hola Mundo   ";
Console.WriteLine(textoConEspacios.Trim()); // "Hola Mundo"

// Contains() -> determina si contiene una subcadena
Console.WriteLine(texto.Contains("Mundo")); // true
Console.WriteLine(texto.Contains("Adiós")); // false
```