# Informe Técnico Final · Proyecto Redes III

> Este documento sirve como base para el informe final (Markdown/PDF). Completar cada sección con evidencia verificable.

## 1. Resumen ejecutivo
- Objetivo del proyecto.
- Alcance técnico.
- Resultado general (qué se logró y con qué nivel de madurez).

## 2. Introducción
- Contexto académico/técnico.
- Problema de seguridad de red abordado.
- Requisitos obligatorios y extras seleccionados.

## 3. Alcance y objetivos
### 3.1 Objetivo general
### 3.2 Objetivos específicos
### 3.3 Supuestos y limitaciones

## 4. Metodología de trabajo por fases
- Checkpoint 1: definición y base.
- Checkpoint 2: consolidación intermedia.
- Checkpoint 3: cierre técnico casi final.
- Entrega final: integración y validación.

## 5. Diseño de topología
### 5.1 Arquitectura lógica
### 5.2 Arquitectura física/laboratorio (GNS3/EVE-NG)
### 5.3 Segmentación por zonas y VLAN
### 5.4 Diseño de DMZ

## 6. Implementación técnica por capas
### 6.1 Capa 2 (L2)
- VLAN, troncales, endurecimiento de puertos.

### 6.2 Capa 3 (L3)
- Enrutamiento inter-VLAN y rutas WAN.

### 6.3 Perímetro y políticas de firewall
- Estrategia default deny.
- Reglas por protocolo/servicio (HTTP/HTTPS/SSH/etc).

### 6.4 VPN
- Tipo de túnel, cifrado, autenticación y validación.

### 6.5 Seguridad Wi-Fi y 802.1X
- Modelo de autenticación.
- Aislamiento de redes corporativa/invitados.

### 6.6 SD-WAN
- Conectividad multisede.
- Gestión centralizada.
- Soporte remoto.

### 6.7 IDS/IPS (Suricata) [si aplica]
- Modo de operación.
- Reglas activas/tuning.
- Casos detectados.

## 7. Análisis CIA aplicado al diseño
### 7.1 Confidencialidad
### 7.2 Integridad
### 7.3 Disponibilidad

> Incluir matriz control ↔ amenaza mitigada ↔ evidencia.

## 8. Control de acceso y autenticación
- Política de identidades.
- AAA/RADIUS/802.1X.
- Principio de mínimo privilegio.

## 9. Pruebas y validaciones
### 9.1 Plan de pruebas
### 9.2 Pruebas funcionales (permitido)
### 9.3 Pruebas negativas (bloqueado)
### 9.4 Pruebas de resiliencia/failover
### 9.5 Evidencia con Wireshark y logs

## 10. Hallazgos de seguridad
- Vulnerabilidades detectadas en el laboratorio.
- Riesgo asociado.
- Mitigación aplicada.
- Riesgo residual.

## 11. Lecciones aprendidas
- Decisiones acertadas.
- Decisiones a mejorar.
- Impacto operativo/administrativo.

## 12. Conclusiones
- Cumplimiento de requisitos obligatorios.
- Extras implementados y valor agregado.
- Estado final de madurez de la arquitectura.

## 13. Referencias
- RFC, guías técnicas, documentación de fabricantes y fuentes académicas.

## 14. Anexos
- Configuraciones completas de dispositivos.
- Tablas de direccionamiento.
- Inventario de reglas de firewall.
- Capturas relevantes y extractos de logs.
