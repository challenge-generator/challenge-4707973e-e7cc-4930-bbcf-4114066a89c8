# Proof of Concept (PoC) - Sistema de Préstamos

## Contexto

Este PoC simula el sistema actual de aprobación de préstamos de la corporación, el cual presenta los siguientes problemas:
- **Acoplamiento alto**: el módulo de aprobación depende directamente de sistemas legacy.
- **Baja escalabilidad**: el proceso de aprobación no soporta más de 100 solicitudes concurrentes.
- **Falta de trazabilidad**: no hay registro de las decisiones de aprobación/rechazo.

El objetivo de este PoC es refactorizar el sistema para:
1. Desacoplar el módulo de aprobación de los sistemas legacy.
2. Implementar un patrón de arquitectura que mejore la escalabilidad.
3. Añadir trazabilidad a las decisiones de aprobación.

## Estructura del PoC

```
/poc
├── loan-approval/
│   ├── legacy/
│   │   ├── LegacyLoanSystem.java       # Simula el sistema legacy de préstamos
│   │   └── LegacyRiskSystem.java      # Simula el sistema legacy de riesgo
│   ├── model/
│   │   ├── LoanApplication.java       # Modelo de solicitud de préstamo
│   │   └── Decision.java              # Modelo de decisión
│   ├── service/
│   │   └── LoanApprovalService.java   # Servicio de aprobación de préstamos
│   └── Main.java                     # Punto de entrada para ejecutar el PoC
└── README.md
```

## Instrucciones para Ejecutar

1. **Compilar y ejecutar**:
   ```bash
   cd poc/loan-approval
   javac Main.java
   java Main
   ```

2. **Salida esperada**:
   ```
   Solicitud de préstamo recibida: ID=12345, Monto=5000.0, Plazo=12
   Consulta a sistema legacy de riesgo...
   Decisión: APROBADO (Score=750)
   ```

## Problemas a Resolver

1. **Desacoplar el módulo de aprobación**: Actualmente, `LoanApprovalService` depende directamente de `LegacyRiskSystem`.
   - **Solución propuesta**: Introducir un contrato (`RiskAssessmentPort`) que defina la interfaz para evaluar riesgos.
   - **Implementar**: Crear una clase `LegacyRiskAdapter` que implemente `RiskAssessmentPort` y envuelva a `LegacyRiskSystem`.

2. **Mejorar escalabilidad**: El sistema actual no soporta concurrencia.
   - **Solución propuesta**: Usar un patrón de arquitectura reactiva o asíncrona (ej. CompletableFuture, Project Reactor).
   - **Implementar**: Modificar `LoanApprovalService` para procesar solicitudes de manera asíncrona.

3. **Añadir trazabilidad**: No hay registro de decisiones.
   - **Solución propuesta**: Introducir un evento `LoanDecisionEvent` y un publicador `DecisionPublisher`.
   - **Implementar**: Crear un `DecisionLogger` que registre cada decisión en una base de datos o archivo.

## Archivos del PoC

### `legacy/LegacyLoanSystem.java`
```java
package legacy;

public class LegacyLoanSystem {
    public String getCustomerInfo(String customerId) {
        // Simula consulta a sistema legacy
        return "Customer: " + customerId + ", Status: ACTIVE";
    }
}
```

### `legacy/LegacyRiskSystem.java`
```java
package legacy;

public class LegacyRiskSystem {
    public int assessRisk(String customerId, double amount) {
        // Simula evaluación de riesgo
        return 750; // Score fijo para el PoC
    }
}
```

### `model/LoanApplication.java`
```java
package model;

public class LoanApplication {
    private String id;
    private String customerId;
    private double amount;
    private int termMonths;

    public LoanApplication(String id, String customerId, double amount, int termMonths) {
        this.id = id;
        this.customerId = customerId;
        this.amount = amount;
        this.termMonths = termMonths;
    }

    // Getters
    public String getId() { return id; }
    public String getCustomerId() { return customerId; }
    public double getAmount() { return amount; }
    public int getTermMonths() { return termMonths; }
}
```

### `model/Decision.java`
```java
package model;

public class Decision {
    private String loanId;
    private String status;
    private int riskScore;

    public Decision(String loanId, String status, int riskScore) {
        this.loanId = loanId;
        this.status = status;
        this.riskScore = riskScore;
    }

    // Getters
    public String getLoanId() { return loanId; }
    public String getStatus() { return status; }
    public int getRiskScore() { return riskScore; }
}
```

### `service/LoanApprovalService.java`
```java
package service;

import legacy.LegacyRiskSystem;
import model.Decision;
import model.LoanApplication;

public class LoanApprovalService {
    private LegacyRiskSystem riskSystem;

    public LoanApprovalService() {
        this.riskSystem = new LegacyRiskSystem();
    }

    public Decision approveLoan(LoanApplication application) {
        int riskScore = riskSystem.assessRisk(application.getCustomerId(), application.getAmount());
        String status = riskScore >= 700 ? "APROBADO" : "RECHAZADO";
        return new Decision(application.getId(), status, riskScore);
    }
}
```

### `Main.java`
```java
import model.LoanApplication;
import model.Decision;
import service.LoanApprovalService;

public class Main {
    public static void main(String[] args) {
        LoanApplication application = new LoanApplication("12345", "CUST123", 5000.0, 12);
        LoanApprovalService approvalService = new LoanApprovalService();
        
        System.out.println("Solicitud de préstamo recibida: ID=" + application.getId() +
                           ", Monto=" + application.getAmount() +
                           ", Plazo=" + application.getTermMonths());
        System.out.println("Consulta a sistema legacy de riesgo...");
        
        Decision decision = approvalService.approveLoan(application);
        System.out.println("Decisión: " + decision.getStatus() +
                           " (Score=" + decision.getRiskScore() + ")");
    }
}
```

---

### Notas para el candidato:
- Refactoriza el código para resolver los problemas identificados.
- Justifica cada cambio con los ASRs del caso (ej. escalabilidad, desacoplamiento).
- El PoC debe seguir siendo funcional después de los cambios.