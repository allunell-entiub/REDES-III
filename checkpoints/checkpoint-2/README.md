# Checkpoint 2 · Avance intermedio (15 de abril)

## Objetivo de la fase
Consolidar seguridad de acceso, cifrado entre sedes y operación multisede con foco en disponibilidad y control de identidad.

## Implementado en esta revisión
- VPN site-to-site estable con validación de conectividad entre segmentos.
- Endurecimiento de reglas de firewall por zona/servicio (HTTP/HTTPS/SSH según necesidad).
- Avance en Wi-Fi segura: integración 802.1X + segmentación de invitados.
- Primer bloque funcional de SD-WAN para conectividad entre sedes.

## Pendiente para siguiente fase
- Afinar políticas IDS/IPS y tratamiento de falsos positivos.
- Pruebas de resiliencia (caída de enlace, failover, degradación).
- Documentar contramedidas frente a Rogue AP / Evil Twin con evidencia.
- Cerrar matriz CIA con trazabilidad por control.

## Hallazgos técnicos clave
- La disponibilidad depende más de diseño de rutas y failover que del ancho de banda nominal.
- 802.1X sin políticas de onboarding claras genera fricción operativa.
- SD-WAN aporta flexibilidad, pero exige observabilidad continua para no perder control.

## Evidencias mínimas esperadas en esta fase
- Pruebas de túneles y cifrado en `evidencias/pruebas/` y `evidencias/wireshark/`.
- Logs de firewall y eventos relevantes de Suricata.
- Topología actualizada y cambios respecto a CP1.
