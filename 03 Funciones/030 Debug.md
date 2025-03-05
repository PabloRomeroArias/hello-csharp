# Debug

Debug es una herramienta que te permite seguir, de manera secuencial la ejecución del código paso a paso. Esto es muy útil para que puedas encontrar errores dentro de tu algoritmo:

- ¿Porqué no se imprime lo que se supone que se tiene que imprimir?
- ¿Por qué lo que se imprime algo distinto a lo que pensabas que se iba a imprimir?

Y muchos otros errores y dudas que te habrán surgido a lo largo de tu camino. Ya no hay excusas, ahora puedes saber en todo momento, el valor de cada variable y por dónde va la ejecución del código

Para debuggear, tienes que indicar en qué punto del código queremos parar la ejecución, estos se llaman **puntos de ruptura** o **breakpoint** en inglés. Si te vas a un archivo de C# (`.cs`), pasa el cursor por la izquierda de las líneas y te debe de aparecer un círculo rojo, si clicas, ese círculo rojo estará con mayor intensidad y ya estará activo. Una vez que tengamos el *breakpoint* (podemos poner tantos como queramos), podrás debuggear con la tecla *F5*. Si no funciona, puedes darle al menú desplegable al lado del botón del play y luego pulsar en la segunda opción que dice: *Debuggear proyecto asociado a este archivo*