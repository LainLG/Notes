
<h2>Sistemas autonomos</h2>

<strong>Autonomoues System: </strong>Es un conjunto de enrutadores que se encuentran bajo una misma administracion.

Los distintos protocolos de enrutamiento pueden clasificarse como:

* Protocolos de enrutamiento <strong>interno</strong> 

* Protocols de enrutamiento <strong>externo</strong>


Una ruta esta conformada por los siguientes elementos:

#### Ruta

* La direccion de la red destino.
* La mascara de la red destino.
* La direccion IP del router adyacente
* El numero de router que hay que atravesar para llegar a la red destino (Saltos).
* La interfaz de red por donde deben retransmitirse los paquetes.

#### Algoritmos de enrutamineto dinamico

* Vector distancia.
* Ruta mas corta
* Estado del enlace.

<h4>Estado de Enlace</h4>

* Descubrir sus vecinos y aprender sus direcciones de redes.
* Medir la demora de cada enlace.
* Construir un paquete que dice que ya todo esta aprendido
* Calcular la ruta a cada router

<h4>Ruta mas corta</h4>

* Numero de saltos.
* Distancia en kilometros del enlace
* La ruta mas corta en los terminos anteriores y mas rapida.
* En general nosotros podemos etiquetar cada arco con un valor que puede ser funcion de:
    *  Ancho de banda.
    * Cantidad de trafico habitual.
    * Longitud de colas promedio
    * Demora,etc.
  
<h4>Open Shortest Path First (OSPF)</h4>

Es el protocolo interior mas utilizado y fue el que remplazo a RIP (Vector Distancia).

Los diseñadores debiean desarrollar un protocolo que cumpliera con los siguientes requisitos:

* Publicarse en la literatura abierta
* Soporte para multiples metricas:
    * Distancia fisica.
    * Demora, etc.
* Tener un algoritmo dinamico que soportara cambios dinamicos de la arquitectura de la red
* Enrutamiento basado en tipo de servicio.
* Balanceo  de carga sobre multiples enlaces.
* Seguridad.

Este protocolo soplorta tres tipos de redes:

* Punto a punto.
* Redes de acceso multiple con difusion (broadcast).
* Redes de acceso multiple sin difusion.

Este protocolo trabaja mediante la utilizacion de un grafo:

* Cda nodo es un enrutador
* Cada arco en un enlace al cual se le asigna un (distancia,demora,.etc)
* Cada red de acceso multiple es representada como un nodo
* Un arcoentre una red y router tiene peso 0
* Permite organizar cada AS en areas numeradas.
* Cada area representa una red o un grupo de redes continuas.
* Las areas no se pueden solapar.
* Todos los enrutadores deben pertenecer a un area.
* Cada AS debe tener un area troncal (area 0).


Podemos encontrar tres tipos de enrutadores:

* Inter Area

* Intra Area

* Inter AS



´