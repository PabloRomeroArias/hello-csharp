# Tipos más comunes

### Tipos de datos más comunes

| Tipo       | Descripción                               | Ejemplo                                  |
|------------|-------------------------------------------|------------------------------------------|
| `string`   | Cadenas de texto                          | `string nombre = "Juan";`                |
| `int`      | Números enteros                           | `int edad = 27;`                         |
| `float`     | Números decimales                         | `float precio = 3.23F;`                   |
| `bool`     | Valores booleanos (`true` o `false`)      | `bool tieneFrio = false;`                |
| `array`    | Una colección de elementos del mismo tipo | `int[] calificaciones = { 1, 2, 3, 4, 5}` |

### Mayoría de tipos

| Tipo         | Descripción                                      | Ejemplo                                                                            |
|--------------|--------------------------------------------------|------------------------------------------------------------------------------------|
| `long`       | Números enteros grandes                          | `long numeroLong = 27L;`                                                           |
| `double`     | Números, decimales grandes                       | `double numeroDouble = 2.7;`                                                       |
| `decimal`    | Decimales de alta precisión                      | `decimal numeroLong = 27M;`                                                        |
| `char`       | Un caracter                                      | `char letra = 'W';`                                                                |
| `list`       | Una colección de elementos del mismo tipo        | `List<string> frutas = [ "platano", "pera" ];`                                     |
| `tuple`      | Una colección de elementos de tipos específicos   | `Tuple<string, int, string> persona = new("Juan", 25, "Romero");`                  |
| `dictionary` | Un mapa de claves y valores                      | `Dictionary<string, int> puntuaciones = new() { {"Pablo", 3}, {"Elisabeth", 5} };` |
| `enum`       | Un conjunto de constantes con nombre             | `enum Color { Rojo, Verde };` `Color color = Color.Verde;`                         |
| `object`     | Cualquier tipo de dato que no sea primitivo      | `object persona = new { Nombre = "Juan", Edad = 25 };`                             |
| `null`       | Un valor nulo                                    | `string? nombre = null;`                                                           |
| `dynamic`    | Un tipo que puede cambiar en tiempo de ejecución | `dynamic variable = "Hola";` `variable = 25;`                                      |