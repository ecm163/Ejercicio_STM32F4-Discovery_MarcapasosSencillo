# Ejercicio_STM32F4-Discovery_MarcapasosSencillo

En éste ejercicio práctico se ha desarrollado software en C para implementarlo en el micro STM32F407VGt6 de la  placa de desarrollo 
STM32F4-Discovery, dicho software simula mediante leds el funcionamiento de un marcapasos sencillo.

NOTA IMPORTANTE: Para explicar de una forma más detallada como ejecutar el programa en su placa y explicar el funcionamiento que 
implementa el software, se ha añadido a éste repositorio un documento PDF.

· ¿Qué hace éste programa cuando se carga en la placa?.

Éste programa simula mediante los 2 Leds de la placa (el naranja y el rojo) el funcionamiento de un marcapasos, de forma que:

- LED Naranja -> representa la frecuencia de pulso cardiaco deseada. Suponemos una duración de medio segundo de sístole 
(corazón contraído), y medio segundo de diástole (corazón expandido).

La sístole se representa con el led naranja encendido, y la diástole con el led naranja apagado.

- LED Rojo -> representa el impulso eléctrico inyectado en el corazón para producir las sístoles (contracciones del corazón). 
Suponemos que es un impulso de corriente eléctrica de duración 10 ms.

La corriente eléctrica inyectada por el marcapasos, produce casi inmediatamente la sístole (o contracción del corazón y bombeo de sangre).
Es por ello que ambas señales se activan a la vez, y por tanto led naranja y rojo se encenderán la vez. 
Sin embargo, la corriente eléctrica necesaria inyectada es sólo un impulso de pequeña duración. Estimamos que basta con un impulso
eléctrico de duración 10 ms para la inyección de corriente, de forma que se mantenga una diástole de medio segundo, y luego una diástole
(expansión del corazón) de otro medio segundo.
Es por ello que el Led rojo permanece encendido bastante menos tiempo que el naranja, sólo un instante.

En éste ejercicio práctico se ha desarrollado software en C para implementarlo en el micro STM32F407VGt6 de la  placa de desarrollo 
STM32F4-Discovery, dicho sofware simula mediante leds el funcionamiento de un marcapasos sencillo.

NOTA IMPORTANTE: Para explicar de una forma más detallada como ejecutar el programa en su placa y explicar el funcionamiento que 
implementa el software, se ha añadido a éste repositorio un documento PDF.

· ¿Qué hace éste programa cuando se carga en la placa?.

Éste programa simula mediante los 2 Leds de la placa (el naranja y el rojo) el funcionamiento de un marcapasos, de forma que:

- LED Naranja -> representa la frecuencia de pulso cardiaco deseada. Suponemos una duración de medio segundo de sístole 
(corazón contraído), y medio segundo de diástole (corazón expandido).

La sístole se representa con el led naranja encendido, y la diástole con el led naranja apagado.

- LED Rojo -> representa el impulso eléctrico inyectado en el corazón para producir las sístoles (contracciones del corazón). 
Suponemos que es un impulso de corriente eléctrica de duración 10 ms.

La corriente eléctrica inyectada por el marcapasos, produce casi inmediatamente la sístole (o contracción del corazón y bombeo de sangre).
Es por ello que ambas señales se activan a la vez, y por tanto led naranja y rojo se encenderán la vez. 
Sin embargo, la corriente eléctrica necesaria inyectada es sólo un impulso de pequeña duración. Estimamos que basta con un impulso
eléctrico de duración 10 ms para la inyección de corriente, de forma que se mantenga una diástole de medio segundo, y luego una diástole
(expansión del corazón) de otro medio segundo.
Es por ello que el Led rojo permanece encendido bastante menos tiempo que el naranja, sólo un instante.

La secuencia sería la siguiente:
--------------------------------------------------------------------
Led rojo y naranja se encienden -> se inyecta corriente eléctrica y comienza la sístole (corazón se contrae).
Transcurre 10 ms.
Led rojo se apaga. -> deja de inyectarse corriente eléctrica.
Transcurre 0,5 sg
--------------------------------------------------------------------
Led naranja se apaga -> se termina la sístole y empieza la diástole (el corazón se relaja y por tanto se expande).
Transcurre 0,5 sg.
--------------------------------------------------------------------
Led rojo y naranja se encienden -> se inyecta corriente eléctrica y comienza la sístole (corazón se contrae).
Transcurre 10 ms.
Led rojo se apaga ->  se termina la sístole y empieza la diástole (el corazón se relaja y por tanto se expande).
Transcurre 0,5 sg
--------------------------------------------------------------------
y así sucesivamente.
      .
      .
      .
      .
Para iniciar el proceso anterior se pulsa el botón “User” de color azul de la placa, y para interrumpirlo se vuelve a pulsar. 
De manera que el botón “User” hace de interruptor del sistema. 

El led verde estará permanentemente encendido como señal de que el programa está cargado en la placa.


Un saludo.



