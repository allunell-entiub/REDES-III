# Checkpoint 3 · Etapa casi final (15 de mayo)

## Objetivo de la fase
Cerrar arquitectura final, controles avanzados y set de evidencias para defensa técnica del proyecto.

## Implementado en esta revisión
- Topología final casi cerrada (VLAN + VPN + Firewall + SD-WAN).
- Integración IDS/IPS (Suricata) con política ajustada por contexto.
- Escenarios de seguridad Wi-Fi con pruebas de ataque/mitigación documentadas.
- Afinación de reglas de acceso para reducir superficie y ruido operativo.

## Pendiente antes de entrega final
- Consolidar informe técnico completo y anexos.
- Limpieza final de configuración y normalización de nomenclatura.
- Ejecutar batería final de pruebas de aceptación y evidencia cruzada.

## Hallazgos técnicos clave
- Menos reglas, más precisas y justificadas, mejora seguridad y operabilidad.
- El valor de IDS/IPS está en el tuning continuo, no en activar reglas por defecto.
- Las pruebas negativas (tráfico bloqueado) son tan importantes como las positivas.

## Evidencias mínimas esperadas en esta fase
- Capturas finales de validación por control.
- Logs de Suricata y firewall correlacionados.
- Artefactos de pruebas de ataques inalámbricos + contramedidas.
