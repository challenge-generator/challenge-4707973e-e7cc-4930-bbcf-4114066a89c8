# Consultoría de Arquitectura para Transformación Digital

Eres un arquitecto senior en una consultora de tecnología que ha sido contratado por una corporación para liderar su transformación digital. La corporación opera en el sector de banca y finanzas, con un portafolio de sistemas heredados y una necesidad urgente de modernización para mantenerse competitivo. Tu tarea es estructurar el entendimiento del negocio y definir el plan de inversión que demuestre el retorno de inversión (ROI) a largo plazo. Debes utilizar el Business Model Canvas y Deloitte Enterprise Value para definir el mapa de capacidades técnicas y el plan de inversión.

## Informacion General

| Campo | Valor |
|-------|-------|
| **Tema** | Arquitectura con enfoque empresarial y frameworks estratégicos |
| **Nivel** | master-l1 |
| **Tipo** | practical |
| **Tiempo estimado** | 180 minutos |

## Fases del Reto

### Fase 0: Configuración del Proyecto

**Objetivo:** Obtener el proyecto base funcional enviando el Código Base a un asistente de IA, que lo analizará, corregirá errores y generará un ZIP listo para usar.

**Tiempo estimado:** 15-30 minutos

**Instrucciones:**

- Asegúrate de tener instalado para ejecutar el proyecto: Un IDE o editor de código.
- Copia todo el contenido del campo **Código Base** de este reto — incluyendo el texto de instrucciones que aparece al inicio.
- Abre un asistente de IA (Claude en claude.ai, ChatGPT o Gemini — se recomienda Claude), pega el contenido copiado en el chat y envíalo.
- El asistente analizará los archivos, corregirá errores y generará un archivo ZIP descargable. Descárgalo y extráelo en la carpeta donde quieras trabajar.
- Verifica que el proyecto arranca sin errores.

**Entregable:** El proyecto compila/arranca sin errores.

<details>
<summary>Pistas de conocimiento</summary>

- Copia el Código Base completo incluyendo el texto de instrucciones al inicio — esas instrucciones le indican al asistente exactamente qué hacer con los archivos.
- Si el asistente no genera el ZIP automáticamente al terminar el análisis, escríbele: "genera el ZIP ahora".
- Si el proyecto tiene errores al arrancar, comparte el mensaje de error con el mismo asistente para que lo corrija.

</details>

### Fase 1: Análisis del Negocio y Entendimiento del Entorno

**Objetivo:** Identificar las necesidades del negocio y el entorno actual de la corporación.

**Tiempo estimado:** 45 minutos

**Instrucciones:**

- Realiza un análisis exhaustivo del negocio de la corporación utilizando el Business Model Canvas.
- Identifica las capacidades técnicas actuales y las brechas que deben ser cubiertas para la transformación digital.

**Entregable:** Diagrama del Business Model Canvas y documento de capacidades técnicas actuales.

<details>
<summary>Pistas de conocimiento</summary>

- Considera las implicaciones de las capacidades técnicas en el ROI a largo plazo.
- Evalúa cómo las brechas identificadas impactan en la competitividad de la corporación.

</details>

### Fase 2: Definición del Mapa de Capacidades Técnicas

**Objetivo:** Definir el mapa de capacidades técnicas que la corporación necesita para su transformación digital.

**Tiempo estimado:** 60 minutos

**Instrucciones:**

- Utiliza el Deloitte Enterprise Value para definir el mapa de capacidades técnicas necesarias.
- Identifica las tecnologías y frameworks que deben ser implementados para cubrir estas capacidades.

**Entregable:** Mapa de capacidades técnicas y documento de tecnologías y frameworks necesarios.

<details>
<summary>Pistas de conocimiento</summary>

- Considera la alineación de las capacidades técnicas con los objetivos de negocio de la corporación.
- Evalúa la viabilidad y el impacto de la implementación de las tecnologías y frameworks identificados.

</details>

### Fase 3: Plan de Inversión y ROI

**Objetivo:** Definir el plan de inversión que demuestre el ROI a largo plazo de la transformación digital.

**Tiempo estimado:** 60 minutos

**Instrucciones:**

- Elabora un plan de inversión detallado que incluya los costos de implementación y los beneficios esperados.
- Calcula el ROI a largo plazo de la transformación digital.

**Entregable:** Plan de inversión detallado y cálculo del ROI a largo plazo.

<details>
<summary>Pistas de conocimiento</summary>

- Considera los costos ocultos y los beneficios indirectos de la transformación digital.
- Evalúa la sostenibilidad del ROI a largo plazo.

</details>

### Fase 4: Presentación y Validación del Plan

**Objetivo:** Presentar y validar el plan de transformación digital ante los stakeholders.

**Tiempo estimado:** 15 minutos

**Instrucciones:**

- Prepara una presentación detallada del plan de transformación digital.
- Valida el plan con los stakeholders y recopila sus comentarios y sugerencias.

**Entregable:** Presentación detallada del plan de transformación digital y documento de comentarios y sugerencias de los stakeholders.

<details>
<summary>Pistas de conocimiento</summary>

- Considera las implicaciones de los comentarios y sugerencias de los stakeholders en el plan de transformación digital.
- Evalúa la viabilidad de implementar los cambios sugeridos.

</details>

## Dimensiones Evaluadas

- **queEs**: ¿Qué es el Business Model Canvas y cómo se utiliza en la consultoría de arquitectura?
- **paraQueSirve**: ¿Para qué sirve el Deloitte Enterprise Value en la definición del mapa de capacidades técnicas?
- **comoSeUsa**: ¿Cómo se utiliza el plan de inversión para demostrar el ROI a largo plazo de la transformación digital?
- **erroresComunes**: ¿Cuáles son los errores comunes al definir un plan de transformación digital y cómo se pueden evitar?
- **queDecisionesImplica**: ¿Qué decisiones implica la presentación y validación del plan de transformación digital ante los stakeholders?

## Criterios de Evaluacion

- Alineación del Business Model Canvas con las necesidades del negocio.
- Definición clara y completa del mapa de capacidades técnicas.
- Plan de inversión detallado y cálculo del ROI a largo plazo.
- Presentación efectiva y validación del plan ante los stakeholders.

## Como trabajar con un asistente de IA

Hay dos caminos, elegi uno:

- **AGENTS.md** (recomendado) — instrucciones nativas del repo. Abri esta carpeta con tu agente local (Claude Code, Cursor, Codex, Copilot, Gemini) y las carga solo. Sabe que archivos faltan y con que comando se verifica, y completa el scaffold escribiendo en disco.
- **PROMPT_MEJORA.md** — para copiar y pegar en un chat (claude.ai, ChatGPT). Devuelve un ZIP con el proyecto. Sirve si no tenes un agente en el IDE.

Ninguno de los dos resuelve las fases del reto: eso es tu trabajo.

## Verificacion

El proyecto esta listo para trabajar cuando este comando corre sin errores:

```bash
python3 -c "import glob,sys; assert glob.glob('adr/*.md') and glob.glob('diagramas/*.mmd'), 'faltan ADRs o diagramas'"
```

---

*Reto generado automaticamente por Challenge Generator - Pragma*
