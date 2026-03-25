# Checkpoint 1 · Definición y primera implementación (18 de marzo)

## Objetivo de la fase
Aterrizar arquitectura base, roles del equipo y primer despliegue funcional con foco en segmentación y control perimetral.

## Implementado en esta revisión
- Diseño inicial de topología (sitio principal + zonas internas).
- VLAN base (usuarios, administración, servidores, invitados).
- Firewall con política inicial (default deny + reglas mínimas de operación).
- Primer planteamiento de VPN y DMZ (aún en hardening).

## Pendiente para siguiente fase
- Cierre de autenticación centralizada (AAA/RADIUS).
- Implementación completa de 802.1X en Wi-Fi corporativa.
- Validación robusta de casos de uso SD-WAN multisede.
- Mayor cobertura de evidencias (tráfico, logs, pruebas negativas).

## Hallazgos técnicos clave
- La segmentación temprana reduce retrabajo al definir reglas de firewall.
- Sin inventario de flujos permitido por aplicación, aparecen reglas ambiguas.
- Es crítico separar tráfico de administración desde el inicio.

## Evidencias mínimas esperadas en esta fase
- Export de configs en `configs/`.
- Capturas de validación básica en `evidencias/wireshark/`.
- Screenshots del laboratorio en `evidencias/gns3-eve/`.
- Logs iniciales de filtrado en `evidencias/firewall-logs/`.
