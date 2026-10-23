# Atributos de Calidad y Escenarios de Calidad

## 1. Introducción
Este documento define los **Requisitos Arquitectónicamente Significativos (ASRs)** para la transformación digital de [Nombre de la Corporación]. Cada ASR incluye un valor medible y escenarios de calidad que describen cómo el sistema debe responder a situaciones específicas.

Los escenarios de calidad siguen el formato estándar de **ISO 25010**:
- **Fuente**: Quien o qué genera el estímulo.
- **Estímulo**: Evento o condición que afecta al sistema.
- **Artefacto**: Parte del sistema afectada.
- **Entorno**: Estado del sistema cuando ocurre el estímulo.
- **Respuesta**: Comportamiento esperado del sistema.
- **Medida**: Métrica cuantificable para evaluar la respuesta.

---

## 2. ASRs Medibles
| ASR                                                                 | Valor Medible                                                                 | Prioridad |
|---------------------------------------------------------------------|------------------------------------------------------------------------------|-----------|
| Reducción del tiempo de procesamiento de transacciones              | Tiempo promedio < 2 segundos (p99 < 3s).                                    | Alta      |
| Disponibilidad de sistemas críticos                                | Uptime del 99.95% para sistemas core.                                        | Alta      |
| Escalabilidad horizontal                                           | Soportar 25,000 TPS con capacidad de escalar a 50,000 TPS en 6 meses.       | Alta      |
| Reducción de costos operativos                                     | Reducción del 30% en 3 años.                                                 | Media     |
| Experiencia del cliente                                            | Tiempo de respuesta promedio < 2 segundos para todas las operaciones.       | Alta      |
| Cumplimiento normativo                                             | 100% de cumplimiento con regulaciones locales e internacionales.             | Alta      |

---

## 3. Escenarios de Calidad
*Completa la siguiente tabla con escenarios de calidad para cada ASR. Utiliza las preguntas guía para orientar tu análisis.*

| ASR                                                                 | Fuente               | Estímulo                          | Artefacto                     | Entorno               | Respuesta                                      | Medida                          |
|---------------------------------------------------------------------|----------------------|-----------------------------------|-------------------------------|-----------------------|------------------------------------------------|---------------------------------|
| Reducción del tiempo de procesamiento de transacciones              | Cliente              | Solicitud de transferencia        | API de Pagos                  | Horario pico          | Procesar la transferencia en < 2 segundos      | Tiempo promedio < 2s (p99 < 3s)|
|                                                                     |                      |                                   |                               |                       |                                                |                                 |
| Disponibilidad de sistemas críticos                                | Sistema externo      | Fallo en un nodo de base de datos | Base de Datos Principal       | Operación normal      | Failover automático en < 30 segundos           | Uptime del 99.95%               |
|                                                                     |                      |                                   |                               |                       |                                                |                                 |
| Escalabilidad horizontal                                           | Carga de trabajo     | Aumento repentino de tráfico      | API Gateway                   | Horario pico          | Escalar horizontalmente sin degradación        | Soportar 25,000 TPS             |
|                                                                     |                      |                                   |                               |                       |                                                |                                 |
| Reducción de costos operativos                                     | Equipo de TI         | Migración a cloud                 | Infraestructura               | Post-migración        | Reducir costos en un 30%                       | Costo operativo reducido en 30% |
|                                                                     |                      |                                   |                               |                       |                                                |                                 |
| Experiencia del cliente                                            | Cliente              | Consulta de saldo                 | Aplicación Móvil              | Horario pico          | Responder en < 2 segundos                       | Tiempo de respuesta < 2s        |
|                                                                     |                      |                                   |                               |                       |                                                |                                 |
| Cumplimiento normativo                                             | Regulador            | Auditoría regulatoria             | Sistema de Reportes           | Operación normal      | Generar reportes en formato requerido          | 100% de cumplimiento            |

---

### Preguntas Guía para Completar los Escenarios de Calidad
1. **Reducción del tiempo de procesamiento de transacciones**:
   - ¿Qué factores podrían aumentar el tiempo de procesamiento (ej. validaciones redundantes, consultas a sistemas externos)?
   - ¿Cómo se podría optimizar el flujo de procesamiento (ej. caching, paralelización)?

2. **Disponibilidad de sistemas críticos**:
   - ¿Qué componentes tienen mayor riesgo de fallo (ej. bases de datos, colas de mensajería)?
   - ¿Qué estrategias de failover podrían implementarse (ej. réplicas activas, health checks)?

3. **Escalabilidad horizontal**:
   - ¿Qué componentes no escalan horizontalmente en la arquitectura actual (ej. bases de datos relacionales)?
   - ¿Qué patrones arquitectónicos podrían mejorar la escalabilidad (ej. eventos, microservicios)?

4. **Reducción de costos operativos**:
   - ¿Qué costos ocultos podrían surgir durante la migración (ej. capacitación, licencias)?
   - ¿Qué beneficios indirectos podrían lograrse (ej. mejora en experiencia del cliente, reducción de fraudes)?

5. **Experiencia del cliente**:
   - ¿Qué operaciones tienen mayor impacto en la experiencia del cliente (ej. login, transferencias)?
   - ¿Cómo se podría medir la experiencia del cliente (ej. encuestas, métricas de rendimiento)?

6. **Cumplimiento normativo**:
   - ¿Qué regulaciones tienen mayor impacto en la arquitectura (ej. GDPR, PCI-DSS)?
   - ¿Qué controles técnicos podrían implementarse para garantizar el cumplimiento (ej. cifrado, logs)?

---

## 4. Métricas y Umbrales
*Define métricas y umbrales para evaluar el cumplimiento de cada ASR.*

| ASR                                                                 | Métrica                                      | Umbral                          | Herramienta de Medición               |
|---------------------------------------------------------------------|----------------------------------------------|---------------------------------|----------------------------------------|
| Reducción del tiempo de procesamiento de transacciones              | Tiempo promedio de procesamiento            | < 2 segundos                   | APM (New Relic, Datadog)               |
| Disponibilidad de sistemas críticos                                | Uptime                                       | 99.95%                         | Monitoreo (Prometheus, Grafana)        |
| Escalabilidad horizontal                                           | Transacciones por segundo (TPS)              | 25,000 TPS                     | Load Testing (JMeter, Gatling)         |
| Reducción de costos operativos                                     | Costo operativo anual                        | Reducción del 30%              | ERP (SAP, Oracle)                      |
| Experiencia del cliente                                            | Tiempo de respuesta promedio                 | < 2 segundos                   | RUM (Real User Monitoring)             |
| Cumplimiento normativo                                             | Número de hallazgos en auditorías            | 0                              | Auditorías internas/externas           |

---

## 5. Priorización de Escenarios
*Prioriza los escenarios de calidad en función de su impacto en el negocio y la viabilidad técnica.*

> **Preguntas guía**:
> - ¿Qué escenarios tienen mayor impacto en los objetivos estratégicos de la corporación?
> - ¿Qué escenarios son más viables técnicamente con los recursos disponibles?
> - ¿Qué escenarios requieren mayor inversión o cambio arquitectónico?