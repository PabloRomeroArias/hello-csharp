# `Enum`s

Los enums

## Syntaxis de `enum`

La sintaxis de una estructura de datos `enum` en C# es la siguiente:

- Palabra reservada `enum`
- Nombre del `enum`
- Abrimos y cerramos bloque de código
- Valores separados por coma

```csharp
enum NombreEnum { Valor1, Valor2, Valor3 }
```

Veamos con un ejemplo real

```csharp
enum DiaSemana { Lunes, Martes, Miercoles, Jueves, Viernes, Sabado, Domingo }

// Para asignar un día de la semana a una variable:
static void Main(string[] args)
{
    DiaSemana dia = DiaSemana.Jueves;
    Console.WriteLine(dia);
}
```

Veamos otro caso de uso de `enum`, en el que se muestra el estado de un pedido

```csharp
enum EstadoPedido { Pendiente, Enviado, Entregado, Cancelado }

static void ActualizarEstadoPedido(EstadoPedido estado) {
    switch (estado) {
        case EstadoPedido.Pendiente:
            Console.WriteLine("El pedido está pendiente.");
            break;
        case EstadoPedido.Enviado:
            Console.WriteLine("El pedido ha sido enviado.");
            break;
        case EstadoPedido.Entregado:
            Console.WriteLine("El pedido ha sido entregado.");
            break;
        case EstadoPedido.Cancelado:
            Console.WriteLine("El pedido ha sido cancelado.");
            break;
        default:
            Console.WriteLine("Estado de pedido no reconocido.");
            break;
    }
}
static void Main(string[] args)
{
    ActualizarEstadoPedido(EstadoPedido.Enviado) // "El pedido ha sido enviado."
}
```