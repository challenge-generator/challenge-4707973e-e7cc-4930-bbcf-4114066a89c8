# Mapa de Capacidades Técnicas - Transformación Digital

## 1. Capacidades Actuales

### Infraestructura Tecnológica
- **Mainframes**: sistemas centrales para procesamiento de transacciones.
- **Servidores legacy**: infraestructura on-premise con baja escalabilidad.
- **Redes**: conectividad limitada a sucursales y centros de datos.

### Aplicaciones y Plataformas
- **Banca en línea**: plataforma web con funcionalidades básicas (consultas, transferencias).
- **Aplicación móvil**: limitada a transacciones simples (saldo, pagos).
- **Sistemas de back-office**: gestión de préstamos, contabilidad y reporting.

### Seguridad y Cumplimiento
- **Autenticación**: basada en usuario/contraseña y tokens.
- **Cifrado**: datos en tránsito y en reposo con estándares básicos.
- **Compliance**: cumplimiento parcial de regulaciones (PCI-DSS, GDPR).

### Datos y Analítica
- **Almacenamiento**: bases de datos relacionales (Oracle, SQL Server).
- **Procesamiento**: batch para generación de reportes.
- **Analítica**: herramientas básicas de BI (Tableau, Power BI).

> Preguntas guía:
> - ¿Qué capacidades actuales son críticas para la operación y deben preservarse?
> - ¿Cuáles son los principales gaps tecnológicos que limitan la transformación?

## 2. Capacidades Futuras

### Infraestructura Tecnológica
- **Cloud computing**: migración a AWS/Azure/GCP para escalabilidad.
- **Contenedores y microservicios**: adopción de Kubernetes y Docker.
- **Redes definidas por software (SDN)**: para mejorar conectividad y seguridad.

### Aplicaciones y Plataformas
- **APIs abiertas**: integración con fintechs y terceros.
- **Plataforma omnicanal**: experiencia unificada en web, móvil y sucursales.
- **Inteligencia artificial**: chatbots, recomendaciones personalizadas y detección de fraudes.

### Seguridad y Cumplimiento
- **Autenticación multifactor (MFA)**: biometría y tokens dinámicos.
- **Zero Trust Architecture**: modelo de seguridad basado en identidad.
- **Blockchain**: para transacciones seguras y trazables.

### Datos y Analítica
- **Data lakes**: almacenamiento escalable para big data.
- **Procesamiento en tiempo real**: Kafka, Flink y Spark.
- **Machine learning**: modelos predictivos para riesgo crediticio y fraude.

> Preguntas guía:
> - ¿Qué capacidades futuras priorizarías y por qué?
> - ¿Cómo alinearías las capacidades técnicas con los ASRs definidos en el caso?

## 3. Roadmap de Implementación

| Fase | Capacidad               | Tecnologías/Frameworks       | Plazo  | Inversión Estimada |
|------|-------------------------|-------------------------------|--------|--------------------|
| 1    | Migración a cloud       | AWS/Azure, Terraform          | 6 meses| $5M                |
| 2    | APIs abiertas           | Spring Boot, OpenAPI          | 4 meses| $2M                |
| 3    | Plataforma omnicanal    | React, Flutter, GraphQL       | 8 meses| $4M                |
| 4    | Seguridad avanzada      | MFA, Zero Trust, Blockchain   | 12 meses| $3M               |
| 5    | Analítica en tiempo real| Kafka, Spark, TensorFlow      | 10 meses| $6M               |

> Preguntas guía:
> - ¿Qué dependencias existen entre las capacidades del roadmap?
> - ¿Cómo ajustarías el roadmap para cumplir con los ASRs en plazos críticos?

## 4. Tecnologías y Frameworks Clave

### Infraestructura
- **Cloud**: AWS (EC2, RDS, Lambda), Azure (AKS, Functions).
- **Contenedores**: Docker, Kubernetes.
- **Redes**: SDN, VPN, CDN.

### Desarrollo
- **Backend**: Spring Boot, Node.js, .NET Core.
- **Frontend**: React, Angular, Flutter.
- **APIs**: REST, GraphQL, gRPC.

### Seguridad
- **Autenticación**: OAuth 2.0, OpenID Connect.
- **Cifrado**: TLS 1.3, AES-256.
- **Blockchain**: Hyperledger Fabric, Ethereum.

### Datos
- **Bases de datos**: PostgreSQL, MongoDB, Cassandra.
- **Procesamiento**: Kafka, Spark, Flink.
- **Analítica**: TensorFlow, PyTorch, Tableau.

> Preguntas guía:
> - ¿Qué criterios usarías para seleccionar tecnologías específicas?
> - ¿Cómo garantizarías la interoperabilidad entre tecnologías nuevas y heredadas?

---

### Notas para el candidato:
- Completa el roadmap con estimaciones realistas de tiempo e inversión.
- Justifica cada capacidad futura con los ASRs del caso.
- Incluye riesgos y mitigaciones para cada fase del roadmap.