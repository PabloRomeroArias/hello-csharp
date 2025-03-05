# Variables y constantes

## Introducción
En programación, las variables y constantes son fundamentales para almacenar y manipular datos. Cuando las usamos, estamos reservando un espacio en memoria RAM. Este espacio de memoria estará reservado durante la vida del programa, es decir, desde que comienza hasta que termina

- Variables: para guardar valores que pueden cambiar (variar)
- Constantes: almacenar valores que **NO** van a cambiar

## Variables
Imagina cajas para guardar tus cosas, cada una con una etiqueta. Cada caja tendrá una forma y tamaño distinto, no es lo mismo guardar zapatos que guardar juegos de mesa. Si queremos saber lo que hay dentro de una caja, primero tendremos que localizar la caja, es decir, buscar la  etiqueta. Una vez que hayamos encontrado la caja, podremos hacer lo que necesitemos con su interios. Por ejemplo, si hay zapatos, salir a la calle, limpiarlos, etc.

Si el ejemplo lo llevamos al mundo de la programación, y más concretamente en **C#** necesitamos lo siguiente:
1. Declarar el tipo y el nombre
   1. Tipo: según la forma de la caja, almacenaremos una cosa u otra
   2. Declaración: tenemos que tener una caja con su respectiva etiqueta, para poder guardar algo en su interior y poder posteriormente encontrar la caja y poder usar lo que hay en su interior
2. Asignar valor a la variable: guardar algo en el interior de la caja
3. Acceder al valor de la variable gracias al nombre: gracias a la etiqueta de la caja, podremos abrirla y hacer lo que queramos con lo que hay en su interior, por ejemplo, imprimir por pantalla

Vamos a ver todo lo que necesitamos para crear una variable en **C#** que almacene nuestro nombre

### Declaración de una variable
1. Tipo de la variable, en este caso `string` o cadena de texto
2. Nombre de la variable: tiene que ser descriptivo. [Cosas a tener en cuenta](#tips)
3. Punto y coma `;` que marca el final de una instrucción

```csharp
string nombre; // Creamos la caja dándole la forma (string) y poniéndole la etiqueta (nombre)
```

Con el código de arriba, hemos declarado una variable con el nombre *nombre* y de tipo *string* (texto)

### Asignación de valor en de una variable
1. Ponemos el nombre de la variable
2. Escribimos el caracter `=`
3. Abrimos y cerramos comillas dobles `""`
4. Asignamos el valor que queramos darle dentro de las comillas dobles

```csharp
nombre = "Pablo"; // Guardamos algo dentro de la caja
```

### Acceder al valor en de una variable
Aquí lo único que necesitaremos es escribir el nombre de la variable. Vamos a acceder al valor de la variable para escribirlo por consola

```csharp
Console.WriteLine(nombre); // Podemos acceder a lo que hay guardado en la caja con etiqueta nombre y hacer lo que queramos con el interior. En este caso, mostrar el valor por pantalla
```

Hay que tener en cuenta, que aunque no imprimamos por pantalla una variable, no significa que no exista, lo que ocurre es que no la vemos. Por otro lado, no es lo mismo acceder al valor para realizar una operación con dicho valor, que imprimir por pantalla, la operación se ha hecho, pero tenemos que imprimir por pantalla para ver los resultados

### Cambiar el valor de una variable
Para cambiar el valor de una variable, lo único que necesitamos es asignarle un nuevo valor a la variable. **Nota:** el valor antiguo se pierde

```csharp
string nombre; // Declaramos la variable
nombre = "Pablo"; // Asignamos un valor
Console.WriteLine(nombre); // Pablo
nombre = "Elisabeth"; // Asignamos otro valor
Console.WriteLine(nombre); // Elisabeth
```

## Creación de constantes
Hay que declarar y crear las constantes fuera de los *métodos*, a nivel de *clase*

1. Palabra reservada `const`
2. Tipo de la constante, en este caso `double` o número decimal preciso
3. Nombre de la constante: tiene que ser descriptivo. [Cosas a tener en cuenta](#tips)
4. Punto y coma `;` que marca el final de una instrucción

Vamos a ver el ejemplo de un código completo haciendo uso de constantes

```csharp
class ConstUdemy
{
   const double NUMERO_PI = 3.1415;
   
   public static void Main(string[] args)
   {
      Console.WriteLine(NUMERO_PI);
   }
}
```

## Tips
Hay que tener en cuenta una serie de cosas a la hora de nombrar las variables y constantes:

Se recomienda no hacer uso de la letra **ñ** ni de **acentos** en el nombre de la variable

El nombre tiene que describir aquello para lo que se ha creado. Si creamos la variable *nombre*, se almacenarán nombres. Aunque no sea un error, se recomienda seguir esta pauta

```csharp
int nombre = 7; // No tiene sentido el nombre
```

Para hacerlo más sencillo, podemos hacer la declaración y asignación de una variable en la misma línea. E incluso omitir el tipo, como en el segundo ejemplo

```csharp
string nombre = "Pablo";
```

## Reglas de variables y constantes
No podemos cambiar el tipo de una variable

```csharp
string nombre = "Pablo";
nombre = 27; // ERROR
```

No se puede hacer uso de espacios para el nombre de las variables
 
```csharp
string nom bre = "Pablo"; // ERROR
```

No se puede hacer uso de las palabras reservadas del lenguaje para dar nombre a las variables

```csharp
string static = "Pablo"; // ERROR
```

No se puede cambiar el valor de una constante

```csharp
class ConstUdemy
{
   const double NUMERO_PI = 3.1415;
   
   public static void Main(string[] args)
   {
      NUMERO_PI = 3.14; // ERROR
   }
}
```