# Funciones Avanzadas

En TypeScript existen varias formas avanzadas de definir y utilizar funciones

## Parámetros de entrada solo lectura

Muchas veces, los parámetros de entrada son solo de lectura. Existe una forma de hacer que no puedas modificarlos para evitar errores y así aumentar la calidad y seguridad del código

```csharp
static void ArgumentoSoloLectura(in int numero)
{
    numero = 3; // Esto da error porque numero es un argumento readonly
}

static void ArgumentoModificable(int numero)
{
    numero = 3;
}
```

## Puntero como parámetro

Existe la posibilidad de pasar a una función la dirección de memoria de un argumento, en lugar de su valor. Gracias a esto, si cambiamos el valor de la función, estaremos cambiando el valor tanto en el ámbito de la función como del alcance de la variable, ya que lo que estamos modificando es el valor correspondiente a la dirección de memoria del puntero

```csharp
static void Main (string[]args)
{
    Punteros(7, out bool esPar); // Pasamos el argumento como puntero y no su valor gracias a la palabra reservada out

    if (esPar)
    {
        Console.WriteLine("Es par");
    }
    else
    {
        Console.WriteLine("Es impar");
    }
}

static void Punteros(in int numero, out bool esPar)
{
    esPar = numero % 2 == 0; // Al asignar valor aquí, tambien se modifica en la llamada, ya que estamos cambiando el valor de la dirección de memoria, no de la variable en sí
}
```

Esto puede ser útil si queremos asignarle valor a varias variables mediante la llamada de una función como en el siguiente ejemplo

```csharp
static void Main (string[]args)
{
    IniciarDatosEntrada(out string nombre, out int edad);

    Console.WriteLine($"Hola {nombre}, tienes {edad} años.");
}

static void IniciarDatosEntrada(out string nombre, out int edad)
{
    Console.Write("Introduce tu nombre: ");
    nombre = Console.ReadLine() ?? "Anónimo";
    Console.Write("Introduce tu edad: ");
    edad = int.Parse(Console.ReadLine() ?? "-1");
}
```

## Nulos
Existe un tipo de dato que es el nulo y es la ausencia de valor

Se representa con un signo de interrogación `?` después del tipo de dato, por ejemplo `int? edad;`. De esta manera, estaremos haciendo edad un entero nulable

Este valor se usa cuando el algoritmo no consigue el resultado esperado, como en el siguiente ejemplo en el que se intenta leer un número por teclado y se devuelve nulo en caso de no haberse introducido número por teclado

```csharp
static void Main (string[]args)
{
    // Edad puede ser nulo
    int? edad = LeerPorTecladoONulo();

    string mensaje = edad != null ? $"Tienes {edad} años" : "No has introducido un número";
    Console.WriteLine(mensaje);
}

static int? LeerPorTecladoONulo()
{
    Console.Write("Introduce tu edad: ");
    string input = Console.ReadLine() ?? "";
    if (int.TryParse(input, out int edad))
    {
        return edad; // Si se convierte, devolvemos la edad
    }
    else
    {
        return null; // Si no se convierte, es que no ha introducido un número y devolvemos nulo
    }
}
```

Si quieres, también puedes hacer uso del operador `??`. Este operador evalúa si el dato de la izquierda es nula, y en caso de ser nula, opta por el dato derecho

```csharp
public static void main(string[] args)
{
    Console.WriteLine(DevolverValorSiNuloConOperador(3)); // 3
    Console.WriteLine(DevolverValorSiNuloConOperador(null)); // 0
}

static int DevolverValorSiNuloConOperador(int? datoNulable)
{
    return datoNulable ?? 0; // Si datoNulable es nulo, se devuelve 0
}
```