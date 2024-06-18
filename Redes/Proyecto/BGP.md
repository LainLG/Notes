<h2> BGP </h2>


### ¿Qué es BGP?

**BGP**, o **Border Gateway Protocol**, es el protocolo estándar de enrutamiento utilizado para intercambiar información de enrutamiento entre sistemas autónomos (AS) en Internet. Un sistema autónomo es un grupo de redes IP bajo una única administración que presenta una política de enrutamiento común al Internet.


### Capa del Modelo TCP/IP donde Funciona BGP

BGP opera en la **Capa de Aplicación** del modelo TCP/IP. Aunque se encarga del enrutamiento entre sistemas autónomos, que es una función de red, se considera parte de la capa de aplicación porque utiliza un protocolo de transporte (TCP) para gestionar las sesiones y el intercambio de mensajes.

### Formato de los Mensajes BGP

Los mensajes BGP tienen un formato específico que incluye las siguientes partes:

- **`Cabecera`**: Incluye un marcador, el tamaño total del mensaje y el tipo de mensaje (OPEN, UPDATE, NOTIFICATION, KEEPALIVE).

- **`Mensaje OPEN`**: Establece una sesión entre dos pares BGP e intercambia parámetros básicos como la versión de BGP, el AS del emisor, el tiempo de espera y el identificador BGP.

- **`Mensaje UPDATE`**: Anuncia nuevas rutas o retira rutas previamente anunciadas. Contiene listas de rutas accesibles junto con sus atributos.

- **`Mensaje KEEPALIVE`**: Mantiene la sesión abierta entre pares BGP y confirma que la conexión está activa.

- **`Mensaje NOTIFICATION`**: Se envía cuando hay un error en la sesión BGP. Contiene un código de error y un mensaje descriptivo.

Cada mensaje tiene su propósito y estructura para asegurar una comunicación eficiente y confiable entre pares BGP.

### ¿Para qué sirve BGP?

BGP es fundamental para la operación de Internet. Permite a los routers de diferentes sistemas autónomos comunicarse entre sí, compartiendo información sobre las rutas disponibles y tomando decisiones inteligentes sobre el mejor camino para enviar paquetes de datos. Aquí hay algunas funciones clave de BGP:

- **`Interconexión de Sistemas Autónomos`**: BGP permite que la red de un AS se conecte y comunique con otras redes AS.

- **`Políticas de Enrutamiento`**: Los administradores de red pueden definir políticas para controlar el flujo del tráfico basándose en necesidades empresariales o acuerdos de nivel de servicio.

- **`Escalabilidad`**: BGP puede manejar grandes cantidades de rutas y es capaz de escalar para soportar el crecimiento de la infraestructura de Internet.

- **`Resiliencia y Estabilidad`**: BGP puede reaccionar a cambios en la topología de la red, como fallas en las conexiones, y recalcula las rutas para asegurar la continuidad del servicio.

- **`Selección de Ruta Óptima`**: BGP selecciona la mejor ruta posible basándose en varios factores, incluyendo la política del AS, la distancia, y la estabilidad del camino.

BGP es un protocolo complejo con muchas características avanzadas que permiten a Internet funcionar como una red interconectada y resiliente.

<hr>

- `configure terminal`: Este comando te lleva al modo de configuración global, donde puedes realizar cambios en la configuración del router.

- `router bgp 100`: Inicia la configuración del Border Gateway Protocol (BGP) con un número de sistema autónomo (AS) de 100.

- `neighbor 160.223.145.18 remote-as 200`: Establece un vecino BGP en la dirección IP 160.223.145.18 que pertenece a otro AS, específicamente el AS 200.

- `redistribute ospf 1`: Toma las rutas aprendidas por el protocolo OSPF (Open Shortest Path First) en la instancia 1 y las redistribuye en BGP, permitiendo que otras redes conozcan estas rutas.

- `router ospf 1`: Inicia la configuración de OSPF para la instancia 1.

- `redistribute bgp 100 subnets`: Redistribuye las rutas aprendidas por BGP en OSPF, incluyendo todas las subredes.

- `end`: Sale del modo de configuración global y regresa al modo EXEC privilegiado.

- `wr`: Guarda la configuración actual en la memoria no volátil para que persista después de un reinicio.

<hr>

### Verificar BGP

Este comando te muestra un resumen del estado de BGP, incluyendo la lista de vecinos BGP, el estado de la sesión (si está establecida o no), el número de prefijos recibidos de cada vecino y más información útil para el diagnóstico.

```bash
show ip bgp summary
```
<hr>


### Implementacion en IPv6

- `configure terminal`: Este comando no cambia.

- `router bgp 100`: Este comando tampoco cambia, ya que defines el AS de la misma manera para IPv4 e IPv6.

- `neighbor 160.223.145.18 remote-as 200`: Deberías reemplazar la dirección IPv4 con la dirección IPv6 del vecino y agregar el comando `address-family ipv6` antes de definir al vecino para especificar que estás configurando BGP para IPv6.

- `redistribute ospf 1`: Este comando se mantiene igual, pero asegúrate de que OSPF esté configurado para soportar IPv6 con OSPFv3.

- `router ospf 1`: Similar al anterior, si estás utilizando OSPFv3 para IPv6, este comando sería `router ospfv3 1`.

- `redistribute bgp 100 subnets`: Este comando también se mantiene, pero asegúrate de que esté dentro del contexto de la familia de direcciones correcta para IPv6.

- `end`: No hay cambios en este comando.

- `wr`: No hay cambios en este comando.
