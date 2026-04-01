## 1. Introducción

En esta entrega se plantea el diseño e implementación de una infraestructura de red segura tomando como base las actividades realizadas durante la asignatura. El objetivo principal es construir una topología funcional que no solo permita la conectividad entre los distintos segmentos de red, sino que además integre mecanismos reales de seguridad, control de acceso y gestión eficiente del tráfico.

El proyecto se centra en una red corporativa segmentada mediante VLANs, protegida por un firewall y con soporte para conexiones seguras (VPN), incluyendo además aspectos más avanzados como seguridad en redes inalámbricas, autenticación mediante 802.1X y una aproximación a entornos SD-WAN para la interconexión de sedes y usuarios remotos .

La idea no es solo que la red “funcione”, sino que esté pensada desde el punto de vista de ciberseguridad, aplicando principios como la confidencialidad, integridad y disponibilidad (CIA), y justificando cada decisión técnica como se haría en un entorno real.



## 2. Organización del trabajo

Desde el inicio del proyecto se planteó una organización bastante clara para evitar improvisaciones. Lo primero que hicimos fue revisar las actividades previas, ya que eran la base obligatoria del diseño. A partir de ahí, dividimos el trabajo en bloques principales:

* Diseño de la topología y direccionamiento
* Configuración de red (VLANs, routing, servicios)
* Seguridad (firewall, DMZ, control de acceso, WiFi seguro)
* Documentación y pruebas

Cada miembro del equipo se encargó de una parte, pero manteniendo siempre una coordinación continua. Por ejemplo, quien diseñaba la topología tenía que coordinarse con quien configuraba el firewall para que las reglas tuvieran sentido según la segmentación planteada.

Para coordinarnos usamos un documento compartido donde íbamos documentando decisiones, cambios y configuraciones. Esto ha sido clave, porque a medida que avanzábamos iban surgiendo ajustes (por ejemplo, cambios en subredes o en reglas de firewall), y sin ese control habría sido un caos.

También se tomaron decisiones importantes al principio, como:

* Usar una topología jerárquica (más escalable)
* Separar servicios en una DMZ
* Aplicar segmentación estricta entre VLANs

Los cambios se han gestionado siempre con lógica: primero se validaban a nivel teórico y luego se aplicaban en el entorno de simulación.



## 3. Idea general del proyecto

El proyecto consiste en implementar una red corporativa segura, segmentada y escalable, capaz de soportar distintos tipos de usuarios y servicios, incluyendo:

* Usuarios internos (empleados)
* Dispositivos inalámbricos
* Servicios públicos (en DMZ)
* Conexiones remotas (VPN)

La necesidad que cubre esta red es la de cualquier empresa moderna: tener conectividad interna y externa, pero con control y seguridad.

Los objetivos principales han sido:

* Separar el tráfico mediante VLANs para evitar accesos no autorizados
* Proteger la red con un firewall bien configurado
* Implementar una DMZ para servicios expuestos
* Asegurar la red WiFi con protocolos adecuados y autenticación
* Permitir acceso remoto seguro
* Preparar la red para escalar (idea de SD-WAN)

Los criterios que hemos seguido han sido realistas:

* Minimizar la superficie de ataque
* Aplicar principio de mínimo privilegio
* Mantener la red ordenada y fácil de administrar



## 4. Topología de red a implementar

Se ha optado por una topología jerárquica, dividida en tres capas:

* Capa de acceso → switches donde se conectan los usuarios
* Capa de distribución → donde se realiza el routing entre VLANs
* Capa de seguridad/perímetro → firewall y salida a Internet

Esta elección se ha hecho porque:

* Es escalable (permite añadir más dispositivos fácilmente)
* Mejora el rendimiento (segmentación del tráfico)
* Facilita la gestión y mantenimiento

La red está segmentada en varias VLANs (por ejemplo: usuarios, administración, invitados, etc.), lo que permite aislar el tráfico. Además, solo se permite comunicación entre VLANs cuando es necesario y siempre controlada por el firewall.

También se ha incluido una DMZ, donde se ubican servicios accesibles desde el exterior (como servidores web), separándolos completamente de la red interna.

La topología también contempla:

* Acceso WiFi seguro
* Posibilidad de conexión entre sedes (enfoque SD-WAN)
* Acceso remoto mediante VPN



## 5. Diseño lógico y físico

A nivel físico, la red se compone de:

* Routers para interconexión y salida a Internet
* Switches (gestionados) para VLANs
* Firewall como elemento central de seguridad
* Puntos de acceso WiFi
* Servidores (incluyendo los de la DMZ)

A nivel lógico:

* Se han definido subredes para cada VLAN
* Routing inter-VLAN controlado
* Firewall con reglas específicas (permitir HTTP/HTTPS, limitar SSH, etc.)
* Implementación de una DMZ para servicios públicos
* VPN para acceso remoto seguro

En la red inalámbrica:

* Uso de protocolos seguros (WPA2/WPA3)
* Autenticación mediante 802.1X
* Medidas contra ataques como Rogue AP o Evil Twin

Cada elemento cumple un rol claro:

* Switches → segmentación
* Router → routing
* Firewall → control y seguridad
* DMZ → aislamiento de servicios públicos



## 6. Metodología de documentación

Toda la documentación del proyecto se ha centralizado en un documento compartido, donde se ha ido guardando:

* Diseño de la topología
* Direccionamiento IP
* Configuraciones de dispositivos
* Reglas de firewall
* Decisiones técnicas y justificaciones
* Resultados de pruebas

Además, se han almacenado los archivos de configuración de los dispositivos, tal como se pide en la entrega.

La documentación se organiza por secciones (topología, seguridad, servicios, etc.), lo que facilita encontrar cualquier información.

Se ha ido actualizando continuamente a medida que avanzaba el proyecto, evitando dejar todo para el final.

Esto es clave en un entorno real, porque:

* Permite reproducir la infraestructura
* Facilita el mantenimiento
* Ayuda en auditorías de seguridad



## 7. Plan de implementación

La implementación se ha planteado en fases:

Primero, diseño y planificación:

* Definición de VLANs y subredes
* Diseño de la topología

Después, configuración base:

* Configuración de switches y VLANs
* Routing entre VLANs

Luego, seguridad:

* Configuración del firewall
* Definición de reglas de tráfico
* Implementación de la DMZ

A continuación, servicios:

* Configuración de servidores
* Implementación de VPN
* Configuración WiFi segura

Finalmente, pruebas:

* Verificación de conectividad
* Test de reglas de firewall
* Validación de aislamiento entre VLANs
* Monitorización del tráfico

El orden es importante: primero se asegura la conectividad básica y luego se añade la seguridad encima.



## 8. Consideraciones técnicas y de seguridad

Durante el diseño se han tenido en cuenta varios aspectos clave:

* Aplicación del modelo CIA:

  * Confidencialidad → segmentación y control de acceso
  * Integridad → control del tráfico y uso de protocolos seguros
  * Disponibilidad → diseño estable y escalable

* Uso de firewall:

  * Filtrado por puertos y protocolos (HTTP, HTTPS, SSH…)
  * Diferenciación entre firewall de red y de aplicación
  * Reglas restrictivas por defecto

* DMZ:

  * Separación de servicios públicos
  * Reducción del riesgo en caso de ataque

* WiFi seguro:

  * Autenticación fuerte (802.1X)
  * Protección contra ataques comunes

* SD-WAN:

  * Enfoque hacia redes distribuidas
  * Mejora del rendimiento y gestión centralizada

También se han previsto posibles problemas:

* Errores de configuración en VLANs
* Reglas de firewall mal definidas
* Problemas de autenticación en WiFi

Para evitarlo, se han hecho pruebas constantes y validaciones en cada fase.



## 9. Conclusión

En este proyecto se ha planteado una red completa, no solo funcional sino también segura y bien estructurada. Se ha trabajado sobre una base real (las actividades), pero llevándola a un nivel más profesional, integrando conceptos avanzados de ciberseguridad.

Se ha seguido una organización clara, con reparto de tareas y coordinación constante. La topología elegida tiene sentido a nivel técnico y permite escalabilidad. Además, toda la información ha sido documentada correctamente, lo que demuestra un enfoque serio y realista.

En conjunto, el proyecto refleja una infraestructura bien pensada, con decisiones justificadas y aplicando buenas prácticas tanto de redes como de seguridad.
