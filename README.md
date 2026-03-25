# REDES III · Topología de Red Segura (GNS3 / EVE-NG)

![Checkpoint 1](https://img.shields.io/badge/Checkpoint%201-Completado-brightgreen)
![Checkpoint 2](https://img.shields.io/badge/Checkpoint%202-En%20progreso-orange)
![Checkpoint 3](https://img.shields.io/badge/Checkpoint%203-Pendiente-lightgrey)
![Entrega Final](https://img.shields.io/badge/Entrega%20final-Pendiente-lightgrey)

Repositorio técnico del proyecto de **Redes III** orientado a diseñar, implementar y validar una red empresarial segura con evolución por fases. El enfoque no es “solo conectar equipos”: es justificar decisiones de seguridad, demostrar controles y dejar evidencia reproducible.

## 1) Objetivo del proyecto

Diseñar e implementar una topología segura en laboratorio (GNS3/EVE-NG) que cumpla los requisitos obligatorios del curso:

- VLAN + Firewall + VPN como base de segmentación y perímetro.
- Aplicación real de CIA (Confidencialidad, Integridad, Disponibilidad).
- Control de acceso y autenticación.
- Seguridad Wi-Fi con 802.1X.
- SD-WAN para conectividad multisede y soporte remoto.

Además, incorporar extras de valor técnico:

- IDS/IPS (Suricata) en modo detección/prevención.
- Análisis de tráfico con Wireshark.
- Pruebas de ataques inalámbricos y contramedidas.

## 2) Topología objetivo (alto nivel)

Arquitectura multisede con separación clara de planos:

- **Capa de acceso (L2):** VLAN de usuarios, servidores, administración, invitados y Wi-Fi corporativa.
- **Capa de distribución/core (L3):** enrutamiento inter-VLAN, políticas de tránsito y rutas hacia WAN.
- **Perímetro:** firewall stateful con reglas explícitas (default deny + allowlist mínima).
- **DMZ:** servicios publicados controlados (p.ej. web interna/externalizada) con filtrado este-oeste y norte-sur.
- **VPN:** túneles site-to-site y/o acceso remoto con autenticación fuerte.
- **Wi-Fi segura:** SSID corporativo con 802.1X/RADIUS + aislamiento de red de invitados.
- **Telemetría y detección:** Suricata + capturas Wireshark para validación de controles.

## 3) Contenidos técnicos cubiertos

- Seguridad de redes avanzada: CIA, acceso, autenticación y endurecimiento.
- Seguridad Wi-Fi: 802.1X, Rogue AP, Evil Twin, segmentación y mitigaciones.
- SD-WAN: conectividad entre sedes, gestión centralizada y operación remota.
- Firewalls: enfoque stateful/proxy, casos de uso y trade-offs.
- Filtrado de protocolos: HTTP/HTTPS/SSH y políticas por zona.
- DMZ: diseño y propósito de servicios expuestos.
- Integración de VLAN + VPN + controles de seguridad.
- IDS/IPS y análisis forense básico de tráfico.

## 4) Estructura del repositorio

```text
.
├── checkpoints/
│   ├── checkpoint-1/
│   │   ├── README.md
│   │   ├── docs/
│   │   ├── configs/
│   │   │   ├── firewall/
│   │   │   ├── routers/
│   │   │   ├── switches/
│   │   │   ├── vpn/
│   │   │   ├── wireless/
│   │   │   └── aaa/
│   │   ├── topology/
│   │   └── evidencias/
│   │       ├── gns3-eve/
│   │       ├── wireshark/
│   │       ├── suricata/
│   │       ├── firewall-logs/
│   │       └── pruebas/
│   ├── checkpoint-2/
│   │   ├── README.md
│   │   ├── docs/
│   │   ├── configs/
│   │   │   ├── firewall/
│   │   │   ├── routers/
│   │   │   ├── switches/
│   │   │   ├── vpn/
│   │   │   ├── wireless/
│   │   │   ├── aaa/
│   │   │   └── sd-wan/
│   │   ├── topology/
│   │   └── evidencias/
│   │       ├── gns3-eve/
│   │       ├── wireshark/
│   │       ├── suricata/
│   │       ├── firewall-logs/
│   │       └── pruebas/
│   └── checkpoint-3/
│       ├── README.md
│       ├── docs/
│       ├── configs/
│       │   ├── firewall/
│       │   ├── routers/
│       │   ├── switches/
│       │   ├── vpn/
│       │   ├── wireless/
│       │   ├── aaa/
│       │   ├── sd-wan/
│       │   └── ids-ips/
│       ├── topology/
│       └── evidencias/
│           ├── gns3-eve/
│           ├── wireshark/
│           ├── suricata/
│           ├── firewall-logs/
│           ├── pruebas/
│           └── ataques-wireless/
├── entrega-final/
│   ├── informe/
│   ├── configs-finales/
│   ├── topology-final/
│   ├── evidencias-finales/
│   │   ├── wireshark/
│   │   ├── suricata/
│   │   ├── firewall-logs/
│   │   └── validaciones/
│   └── anexos/
├── docs/
│   ├── diseno/
│   ├── plantillas/
│   └── operacion/
├── scripts/
│   ├── provisioning/
│   ├── backup/
│   └── validacion/
├── .gitignore
└── README.md
```

## 5) Navegación rápida

- Estado de avance por fase:
  - [Checkpoint 1](./checkpoints/checkpoint-1/README.md)
  - [Checkpoint 2](./checkpoints/checkpoint-2/README.md)
  - [Checkpoint 3](./checkpoints/checkpoint-3/README.md)
- Template del informe técnico final:
  - [Plantilla](./docs/plantillas/informe-tecnico-template.md)
- Entrega consolidada:
  - [`/entrega-final`](./entrega-final)

## 6) Decisiones de diseño (registro vivo)

> Esta sección se actualiza en cada checkpoint con justificación técnica y evidencia.

- **Segmentación por VLAN + ACL/Firewall entre zonas:** reducir superficie de ataque y limitar movimiento lateral.
- **Default deny en perímetro y tránsito inter-zona:** abrir solo flujos necesarios y documentados.
- **VPN para tráfico entre sedes y acceso remoto:** proteger datos en tránsito fuera de LAN confiable.
- **802.1X para Wi-Fi corporativa:** eliminar dependencia de clave compartida y mejorar trazabilidad por usuario/dispositivo.
- **DMZ para servicios expuestos:** separar servicios públicos de activos internos críticos.
- **IDS/IPS + captura selectiva:** detectar patrones anómalos y validar hipótesis con tráfico real.

## 7) Criterio de evidencia técnica

Todo control implementado debe estar respaldado con:

1. Configuración versionada (router/switch/firewall/IDS).
2. Prueba de funcionamiento (captura, log o comando de verificación).
3. Resultado esperado vs. resultado observado.
4. Riesgo mitigado o brecha identificada.

## 8) Estrategia de commits (historial con narrativa técnica)

Formato recomendado:

```text
[Fase X][Componente] acción breve orientada a seguridad
```

Ejemplos:

- `[CP1][TOPO] Define segmentación inicial VLAN + zonas de seguridad`
- `[CP1][FW] Implementa política base default-deny y reglas mínimas`
- `[CP2][VPN] Levanta túnel site-to-site y valida cifrado`
- `[CP2][WIFI] Integra 802.1X con RADIUS para SSID corporativo`
- `[CP3][IDS] Activa reglas Suricata y documenta falsos positivos`
- `[FINAL][DOC] Cierra informe técnico con matriz CIA y evidencias`

Buenas prácticas:

- Un commit = un cambio técnico coherente.
- Mensajes con impacto de seguridad (qué riesgo cubre).
- Referenciar evidencia cuando aplique (`evidencias/...`).
- Evitar commits “update” sin contexto.

---

Si este repositorio se mantiene con disciplina (config + evidencia + justificación), sirve no solo para aprobar, sino para demostrar criterio real de ingeniería de seguridad en red.
