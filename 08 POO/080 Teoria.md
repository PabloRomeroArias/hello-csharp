# Programación Orientada a Objetos

## Introducción

Hasta ahora, hemos usado **C#** como un lenguaje *imperativo* y más concretamente *procedimental*. Estos términos se refieren a **paradigmas de programación**

Un paradigma de programación se le llama a la manera en que clasificamos a los lenguajes de programación según sus características. Los paradigmas de programación comunes son:

1. Imperativo
   1. Procedimental
   2. Orientado a Objetos
2. Declarativo
   1. Funcional
   2. Lógico
   3. Matemético
   4. Reactivo

### 1. Imperativo

En este paradigma de programación, el programador le dice a la máquina cómo tiene que cambiar su estado mediante instrucciones. Es considerado el paradigma de programación más antiguo. Según este, un programa es *una secuencia claramente definida de instrucciones para un ordenador*

En programación imperativa, el código fuente (tu código) encadena una serie de instrucciones que determinan lo que debe hacer un ordenador en cada intrucción para alcanzar el resultado deseado. Los valores en las variables se modifican mientras el programa se ejecuta. Para gestionar las instrucciones, se integran estructuras de control como bucles o estructuras anidadas en el código fuente

#### 1.1 Programación procedimental

Este paradigma de programación es aplicable tanto en lenguajes de programación de bajo nivel como en lenguajes de alto nivel. En caso de que esta técnica se aplique en lenguajes de alto nivel, será muy parecido al *paradigma de programación declarativo funcional*

Este paradigma ofrece muy buena eficiencia durante la ejecución del programa debido a que no tiene una carga de memoria alta para los procesadores modernos. También cabe señalar que es muy complicado y poco recomendable hacer uso de programación procedimental pura

#### 1.2 Programación Orientada a Objetos (POO)

En este paradigma de programación imperativa, partimos del concepto **objeto** como base. Un objeto tiene propiedades (**atributos**) y funciones (**métodos**)

### 2 Declarativo

En ete paradigma de programación, el programador declara las propiedades del resultado deseado, pero no cómo calcularlo. Se detalla el resultado deseado con cierto código fuente, pero no se detallan los pasos a seguir para conseguir dicho resultado

Una ventaja de este paradigma es que tiene la capacidad de describir problemas de forma más corta y precisa que un lenguaje imperativo

#### 2.1 Programación funcional

Es un paradigma declarativo basado en el uso de *funciones matemáticas*. Explicado resumidamente, una magnitud es función de otra si el primer valor depende del segundo valor. En un ejemplo real, el área de una circunferencia depende de su radio, por lo que la primera magnitud (área) depende de la segunda (radio)

En este estilo de programación, se hace uso de funciones. La expresión de una función se puede asignar a una variable como si se tratara de un tipo cualquiera de dato e incluso se pueden crear funciones de orden superior. Una función es de orden superior si cumple con al menos una de las siguientes condiciones:

1. Puede tomar una o más funciones como entrada
2. Puede devolver una función como salida

#### 2.2 Lógico

Es un paradigma declarativo en el que el resultado deseado se declara como la respuesta a un a pregunta sobre un sistema de hechos y reglas

#### 2.3 Matemático

Es un paradigma declarativo en el que el resultado deseado se declara como la solución de un problema de optimización

#### 2.4 Reactivo

Es un paradigma declarativo en el que se declara el resultado deseado con flujos de datos y propagación del cambio

## Programación Orientada a Objetos

### 1. Fundamentos de la POO

#### Clase

Una clase es una especie de *plantilla* en la que se definen las propiedades (**atributos**) y las funciones (**métodos**) predeterminados de un tipo de objeto. Esta plantilla se crea para poder crear objetos fácilmente. Cuando creamos un objeto a partir de una plantilla *clase*, se dice que estamos **instanciando** un objeto de tipo *clase*

#### Objeto

Es la instancia de una clase. Es una entidad con un conjunto de atributos y comportamientos (métodos)

#### Atributo

Propiedades o características que tiene una clase

#### Constructor

Un constructor es un **método especial** de las clases que se usa para **instanciar** objetos. Cuando creamos un objeto, esta función es llamada y de esta manera podemos asociarle valor a los atributos del objeto directamente

#### Método

Función o algoritmo que un objeto tiene capacidad de hacer

### 2. Caracterísitcas de la POO

#### Abstracción

La abstracción consiste en definir las características esenciales de un objeto. De esta manera, cada objeto se comporta como un agente en el programa, siendo capaz por sí mismo de cambiar sus propiedades, realizar funciones y comunicarse con otros objetos del sistema sin decir cómo se implementan sus características y desconociendo cómo se implementan la de aquellos objetos con los que se comunican

De esta manera, estamos aislando un elemento de su contexto y del resto de elementos que lo acompañan, así podemos hacer énfasis en el *qué se hace* y no tanto en el *cómo se hace*, a esto se le conoce como característica de **caja negra**

#### Modularidad

Propedad que permite subdividir una aplicación en partes más pequeñas (módulos). Cada una de las partes debe ser **tan independiente** como sea posible de la aplicación en sí y dee las restantes partes. Los lenguajes soportan la modularidad de diversas formas, normalmente mediante uso de librerías propias del lenguaje o definidas por el programador

#### Encapsulamiento

Significa reunir todos los elementos comunes de una entidad, pertenecientes al mismo nivel de abstracción. De esta manera aumentamos la cohesión de los componentes del sistema, permitiendo así hacer nuestro programa modulable. Al igual que en la *modularidad*, los lenguajes soportan la encapsulación de diversas formas

#### Herencia

Jerarquía de clases que se crea cuando en nuestro programa tenemos dos clases que comparten atributos y métodos. De esta manera, evitamos duplicidad de código, mayor mantenibilidad y escalabilidad. Esto lo podemos conseguir gracias a una buena abstracción

#### Polimorfismo

Se refiere a la posibilidad de enviar mensajes sintácticamente iguales a *objetos* de *tipo* distinto