# Funciones

Las funciones son bloques de código reutilizables que realizan un algoritmo específico. Sirven para estructurar y organizar el código

## Declaración de funciones

Para declarar una función, necesitamos lo siguiente:
- Sitúate en el bloque de código de la clase
- Haz uso de las palabras reservadas `static void`
- Nombra de la función con la primera letra en mayúsculas
- Abre y cierra paréntesis `()`
- Abre y cierra bloque de código `{}`
- Escribe las sentencias dentro del bloque de código

```csharp
class Prueba
{
    static void Main(string[]args)
    {
       Console.WriteLine("Estamos en el método Main");
    }

    static void Saludar() // A esta línea se llama firma de la función
    {
        // Sigue siendo secuencial, las instrucciones se siguen ejecutando una detrás de otra
        Console.WriteLine("Hola, te saludo desde el primer método!");
        Console.WriteLine("Segunda sentencia del método");
        Console.WriteLine("Tercera sentencia del método");
    }
}
```

Si ejecutamos , vemos que no ocurre nada, esto se debe a que hemos declarado la función, está creada, pero en ningún momento le estamos diciendo a nuestro flujo principal del programa que tiene que ejecutar el bloque de código de la función

Lo único que tenemos que hacer para que se ejecute, es llamar a la función por su nombre, seguido de apertura y cierre de paréntesis, tal y como se muestra a continuación

```csharp
Saludar();
```

La ejecución del código sigue siendo secuencial, es decir, una línea detrás de otra. Si llegamos a la llamada a una función, se dará un salto y se ejecutarán las líneas de código de dicha función, una vez que se ejecuten, volveremos al bloque de código que ha llamado a la función y se seguirán ejecutando secuencialmente las sentencias

```csharp
Console.WriteLine("Me ejecuto antes del método");
Saludar();
Console.WriteLine("Hemos vuelto de la función saludar, seguimos hacia abajo");
```

Y como hemos dicho anteriormente, las funciones son reutilizables, es decir, podemos llamarlas las veces que necesitemos durante el tiempo de vida de nuestro programa

```csharp
Saludar();
Saludar();
Saludar();
```

## Parámetros de entrada

En muchas ocasiones, las funciones necesitan datos de entrada (variables) para poder realizar aquello para lo que han sido creadas, por ejemplo, si queremos saludar a alguien por su nombre, necesitaremos una variable y dependiendo del valor de ésta, se imprimirá una cosa u otra

Para que la función sea capaz de recibir parámetros de entrada, tendremos que declararlos en la firma de la función:

```csharp
// Parámetro de entrada entre los paréntesis () del nombre
static void SaludarPersona(string nombre)
{ // nombre de la variable seguido de : y el tipo de dato
    Console.WriteLine($"Hola ${nombre}, te saludo desde un método.");
}
```

Y ahora, además de llamar a la función, tenemos que pasarle el argumento. Ya sea pasándole el dato *hardcodeado* o mediante una variable

```csharp
SaludarPersona(); // Da error

// Pasamos el valor del dato hardcodeado
SaludarPersona("Jaimito");

// Pasamos el valor del dato de la variable
string nombre = "Pablo";
SaludarPersona(nombre);
```

Podemos pasar tantos argumentos como sean necesarios, por ejemplo, para la suma de dos números cualesquiera. La única diferencia es que los argumentos van separados por coma:

```csharp
static void Sumar(int a, int b) {
    int suma = a + b;
    Console.WriteLine($"Sumita ${a} + ${b} = ${suma}");
}
```

Y ahora solo tendríamos que llamar a la función sumar para que ejecute sus sentencias

```csharp
Sumar(3, 5); // 8
Sumar(100, -4); // 96

int num1 = 13;
int num2 = 1;
Sumar(a, b); // 14
```

Se recomienda que cuando una función tenga muchos argumentos, para que la firma sea más legible, se use una línea para cada argumento, tal y como se muestra en el siguiente ejemplo

```csharp
static void SumarMuchosNumeros(
    a : number,
    b : number,
    c : number,
    d : number,
    e : number,
    f : number,
) {
    int suma = a + b + c + d + e + f;
    Console.WriteLine($"Suma de muchos números\n${a} + ${b} + ${c} + ${d} + ${e} + ${f} = ${suma}");
}
```

## Alcance de una función

### Alcance de una función

El alcance de una función se refiere a la visibilidad, privacidad y accesibilidad de las variables dentro y fuera de la función. En *csharp*, los argumentos y variables declaradas dentro de una función tienen un ámbito local. Esto significa que nadie fuera de la función podría acceder a ese valor, como se muestra en el siguiente ejemplo

```csharp
static void Main(string [] args)
{
    Console.WriteLine($"Sumita ${a} + ${b} = ${suma}") // ERROR
}

static Sumar(int a, int b) {
    int suma = a + b;
    Console.WriteLine($"Sumita ${a} + ${b} = ${suma}");
}
```

En este ejemplo, cuando intentamos mostrar por pantalla el mensaje fuera del alcance de la función nos da error ya que no se pueden encontrar las variables *a*, *b* ni *suma*

Además aunque tengamos declarada las variables con el mismo nombre, no serán las mismas, hagamos el ejemplo con suma

```csharp
static void Main(string [] args)
{
    Sumar(3, 7); // El valor de suma es 10
    int suma = 0;
    Console.WriteLine($"Valor variable suma en método principal: ${suma}"); // 0
}

static void Sumar(int a, int b)
{
    int suma = a + b;
    Console.WriteLine($"Sumita ${a} + ${b} = ${suma}");
}
```

Como hemos dicho al principio, una función es un bloque de código que realiza un algoritmo específico, es una buena práctica llevar esto a raja tabla, ya que de esta manera nuestro código tendrá menos errores, será más escalable y más mantenible

A partir de ahora, te recomiendo que hagas uso de funciones para prácticamente todo. Si no se hace, pronto tendrás lo que se llama código *spaguetti*, que no es más que aquel código que se escribe de manera totalmente secuencial, sin hacer uso de funciones

## Parámetros de salida

Imaginemos que tenemos una función que calcula la media aritmética de dos números, tal y como se muestra en el siguiente ejemplo

```csharp
static void MediaAritmetica(int a, int b) {
    float media = (a + b) / 2f;

    Console.WriteLine($"La media aritmética de ${a} y ${b} es: ${media}");
}
```

Esta función no solo calcula la media aritmética de dos números, también muestra por pantalla el resultado. Si en algún otro lugar de nuestro programa necesitamos la media aritmética y llamamos a nuestra función, no solo vamos a calcular la media aritmética, sino que vamos a ejecutar el bloque de código de la función. Además, una vez se ejecute el bloque de código de la función, el valor calculado se pierde

En muchas ocasiones, necesitaremos que los métodos devuelvan el resultado del algoritmo que resuelven para nosotros poder seguir realizando otras tareas. Para ello se usan los valores de salida.

Para que la función sea capaz de devolver parámetros de salida, tendremos que declarar el **tipo** de retorno en la firma de la función, detrás de los paréntesis de los argumentos. Por último, en el cuerpo de la función se tiene que hacer uso de la palabra reservada `return`:

```csharp
static float MediaAritmetica(int a, int b)
{ // En la firma decimos el tipo de retorno, en este caso un number
    float media = (a + b) / 2f;

    return media; // Esta línea es la que se encarga de devolver el valor calculado en el algoritmo de la función, en este caso la media aritmética
    Console.WriteLine("Yo nunca me ejecutaré"); // Nunca se va a ejecutar este bloque de código
}
```

Ahora, nuestra función ya devuelve un valor, lo que queda es, a parte de llamar a la función para que se ejecute su bloque de código, debemos recoger el valor devuelto

```csharp
// Por ejemplo, asignar el valor a una variable
float media = MediaAritmetica(3, 1); // Los parámetros de entrada siguen siendo necesarios

// Ahora que tenemos el valor, podemos usarlo para lo que necesiteos, por ejemplo, enviarlo a otro método cuyo argumento de entrada no es un simple número, sino la media aritmética
CalculosEstadisticosComplejos(media);
```

Como hemos dicho al principio, una función es un bloque de código que realiza un algoritmo específico, es una buena práctica llevar esto a raja tabla, ya que de esta manera nuestro código tendrá menos errores, será más escalable y más mantenible

A partir de ahora, te recomiendo que hagas uso de funciones para prácticamente todo. Si no se hace, pronto tendrás lo que comúnmente se llama código *spaguetti*, que no es más que aquel código que se escribe de manera totalmente secuencial, sin hacer uso de funciones y que se rompe con bastante facilidad