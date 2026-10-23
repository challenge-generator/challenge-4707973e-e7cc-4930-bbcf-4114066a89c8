# AGENTS.md

Instrucciones para el agente de IA que abra este repositorio (Claude Code, Cursor, Codex, Copilot, Gemini). Se cargan solas: no hay que pegar nada en ningun chat.

## Que es este repositorio

Es el codigo base de un reto de aprendizaje de Pragma: **Consultoría de Arquitectura para Transformación Digital**.

| | |
|---|---|
| Tema | Arquitectura con enfoque empresarial y frameworks estratégicos |
| Nivel | master-l1 |
| Chapter | Arquitectura |
| Especialidad | Soluciones |
| Stack | Markdown / Business Model Canvas + Deloitte Enterprise Value |
| Patron arquitectonico | Consultoría de Arquitectura Empresarial con enfoque en valor estratégico |
| Tiempo estimado | 180 minutos |

## Receta del stack

Esqueleto obligatorio:

- `adr/`
- `arquitectura.md`
- `diagramas/*.mmd`
- `atributos-de-calidad.md`
- `rubrica-autoevaluacion.md`
- `poc/ (opcional)`

Dependencias:

- Mermaid.js n/a
- Deloitte Enterprise Value Framework (documentación) n/a
- Business Model Canvas (template) n/a
- Plantilla ADR (formato Markdown) n/a
- C4 Model para diagramas de arquitectura n/a

## Tu tarea

Dejar este conjunto de artefactos en estado **verificable**: que el comando de verificacion corra sin errores. Escribi los archivos en disco, en este repositorio. No generes ZIPs ni archivos adjuntos.

En orden:

1. Corre `python3 -c "import glob,sys; assert glob.glob('adr/*.md') and glob.glob('diagramas/*.mmd'), 'faltan ADRs o diagramas'"` y mira que falla.
2. Completa lo que falte de la lista de abajo: manifiesto de dependencias, punto de entrada, capa de interfaz y las capas del patron declarado.
3. Arregla SOLO los errores que impiden compilar o arrancar.
4. Volve a correr `python3 -c "import glob,sys; assert glob.glob('adr/*.md') and glob.glob('diagramas/*.mmd'), 'faltan ADRs o diagramas'"` hasta que pase.
5. Pará ahí.

## Regla dura: las fases son trabajo del humano

**PROHIBIDO implementar los entregables de las fases.** El valor del reto esta en que la persona los resuelva. Tu trabajo es que tenga un proyecto que arranca; el hueco pedagogico se queda como esta.

No resuelvas nada de esto:

- **Fase 1 — Análisis del Negocio y Entendimiento del Entorno**: Diagrama del Business Model Canvas y documento de capacidades técnicas actuales.
- **Fase 2 — Definición del Mapa de Capacidades Técnicas**: Mapa de capacidades técnicas y documento de tecnologías y frameworks necesarios.
- **Fase 3 — Plan de Inversión y ROI**: Plan de inversión detallado y cálculo del ROI a largo plazo.
- **Fase 4 — Presentación y Validación del Plan**: Presentación detallada del plan de transformación digital y documento de comentarios y sugerencias de los stakeholders.

Distincion operativa:

- **Arreglar** (si): import faltante, tipo que no existe, dependencia sin declarar, error de sintaxis, archivo referenciado que no existe.
- **No tocar** (no): logica de negocio incompleta, validaciones ausentes, secretos hardcodeados, APIs deprecadas que funcionan, concurrencia insegura, patrones mejorables. Eso es lo que la persona tiene que encontrar.

## Superficie de practica (NO completes)

Estos archivos SON el ejercicio de la persona. No los implementes; deja stubs. No toques la logica que el reto pide completar.

- [ ] `adr/001-transformacion-digital.md` — El topic pide decisiones de arquitectura: el ADR es el ejercicio.
- [ ] `adr/002-inversion-tecnologica.md` — El topic pide decisiones de arquitectura: el ADR es el ejercicio.

## Lo que falta y tenes que completar

No se detectaron huecos: estan los archivos declarados, el boilerplate del stack y ninguna referencia quedo colgando. Igual corre el comando de verificacion — que los archivos existan no garantiza que compilen.

### Presentes (13)

- `docs/business-model-canvas.md`
- `docs/mapa-capacidades-tecnicas.md`
- `docs/plan-inversion-roi.md`
- `presentations/transformacion-digital.pptx.md`
- `poc/README.md`
- `arquitectura.md`
- `README.md`
- `atributos-de-calidad.md`
- `riesgos-y-mitigaciones.md`
- `rubrica-autoevaluacion.md`
- `diagramas/contexto.mmd`
- `adr/001-transformacion-digital.md`
- `adr/002-inversion-tecnologica.md`

### Capas del patron declarado

Cada una tiene que existir como directorio real con al menos un archivo. Codigo plano en la raiz no satisface el patron.

- `analisis-negocio`
- `mapa-capacidades`
- `plan-inversion`
- `presentacion`
- `diagramas`
- `adr`

## Verificacion

```bash
python3 -c "import glob,sys; assert glob.glob('adr/*.md') and glob.glob('diagramas/*.mmd'), 'faltan ADRs o diagramas'"
```

El comando tiene que pasar SIN implementar los archivos de la superficie de practica: solo andamiaje.

Ese comando pasando es la definicion de "terminado" para vos.

## Convenciones que tenes que respetar

- Un solo ecosistema: no declares librerias de otro lenguaje ni mezcles gestores de paquetes.
- Toda libreria que uses tiene que estar declarada en el manifiesto de dependencias.
- Todo import declarado tiene que usarse; todo tipo usado tiene que existir o venir de una dependencia declarada.
- El patron es **Consultoría de Arquitectura Empresarial con enfoque en valor estratégico**: los contratos (interfaces, puertos) los define la capa interna y los implementa la externa, nunca al revés.
- Los archivos que crees llevan implementacion real, no stubs: sin `TODO`, sin cuerpos vacios, sin `// getters y setters`.

## Contexto del candidato

Sirve para calibrar el nivel del codigo, no para resolver las fases.

- Perfil: Chapter Arquitectura, Especialidad Soluciones, Master
- Brecha que el reto ataca: Realiza procesos de consultoría de arquitectura: Ha usado Frameworks para el entendimiento de Negocio como descubrimiento bottom up, front to back, back to front, top-down, Business Canvas Model, Deloitte Enterprise Value.
- Mision: Profesional senior con experiencia en consultoría y diseño de soluciones empresariales

---

*Generado por Challenge Generator — Pragma. `README.md` tiene el enunciado completo del reto para la persona. `PROMPT_MEJORA.md` es la variante para pegar en un chat, si se prefiere ese flujo.*
