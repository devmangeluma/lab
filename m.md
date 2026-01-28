# BMAD-METHOD: Análisis Completo del Repositorio

> **Versión analizada**: 6.0.0-Beta.2 (enero 2026)
> **Licencia**: MIT
> **Última actualización del análisis**: 28 de enero de 2026

---

## 1. ¿Qué es BMAD-METHOD?

**BMAD-METHOD** significa **"Breakthrough Method of Agile AI-driven Development"** — es un framework de desarrollo de software impulsado por IA que integra metodología ágil con agentes de IA especializados.

### Filosofía Core

> **"Human Amplification, Not Replacement"** — amplificación humana, no reemplazo.

A diferencia de herramientas tradicionales de IA que hacen el trabajo *por ti* (produciendo resultados mediocres), BMAD proporciona **agentes expertos que colaboran contigo** a través de flujos de trabajo estructurados.

### Características Principales

| Característica | Detalle |
|----------------|---------|
| **Agentes especializados** | 9 agentes en el módulo base (BMM) |
| **Flujos de trabajo** | 50+ workflows guiados |
| **Escalabilidad** | Desde bug fixes hasta sistemas empresariales |
| **Ciclo completo** | Brainstorming → Deployment |
| **Open Source** | 100% libre, sin paywalls |
| **IDEs compatibles** | Claude Code, Cursor, Windsurf, Roo Code |

---

## 2. Estructura del Repositorio

```
BMAD-METHOD/
├── src/                           # Código fuente principal
│   ├── bmm/                       # BMad Method Module (módulo principal)
│   │   ├── agents/               # 9 agentes especializados
│   │   ├── workflows/            # Flujos de trabajo por fase
│   │   ├── teams/                # Definiciones de equipos (party mode)
│   │   ├── data/                 # Datos y plantillas
│   │   └── testarch/             # Arquitectura de pruebas (TEA)
│   ├── core/                      # Núcleo de BMAD
│   │   ├── agents/               # BMad Master agent
│   │   ├── workflows/            # Workflows fundamentales
│   │   ├── resources/            # Recursos compartidos
│   │   └── tasks/                # Tareas disponibles
│   └── utility/                   # Componentes de utilidad
│
├── tools/                         # Herramientas de infraestructura
│   ├── cli/                       # CLI principal (Commander.js)
│   │   ├── commands/             # Comandos (install, status)
│   │   ├── installers/           # Lógica de instalación
│   │   └── lib/                  # Librerías compartidas
│   ├── schema/                    # Validación de esquemas (Zod)
│   └── flattener/                # Aplanador de documentos
│
├── docs/                          # Documentación completa
│   ├── tutorials/                 # Tutoriales paso a paso
│   ├── how-to/                    # Guías prácticas
│   ├── explanation/              # Conceptos y arquitectura
│   └── reference/                # Documentación técnica
│
├── website/                       # Sitio de documentación (Astro + Starlight)
├── test/                          # Suite de pruebas (Jest)
└── .github/                       # GitHub Actions y CI/CD
```

### Estructura en Proyectos Instalados

Cuando instalas BMAD en tu proyecto, crea:

```
tu-proyecto/
├── _bmad/                         # Instalación de BMAD
│   ├── bmm/                       # Módulo BMM instalado
│   │   ├── agents/               # Agentes compilados
│   │   ├── workflows/            # Workflows disponibles
│   │   └── config.yaml           # Configuración del módulo
│   └── _config/                   # Configuración global
│       ├── config.yaml           # Config principal
│       ├── agent-manifest.csv    # Manifest de agentes
│       ├── workflow-manifest.csv # Manifest de workflows
│       └── task-manifest.csv     # Manifest de tareas
│
└── _bmad-output/                  # Salida de artefactos
    ├── planning-artifacts/        # PRDs, Architecture, UX
    ├── implementation-artifacts/  # Stories, Reviews
    └── docs/                       # Documentación generada
```

---

## 3. Arquitectura de 4 Fases

BMAD organiza el desarrollo en **4 fases secuenciales**:

### Fase 1: ANALYSIS (Opcional)

Comprende tu proyecto mediante investigación guiada.

| Workflow | Agente | Salida |
|----------|--------|--------|
| `brainstorm-project` | Mary (Business Analyst) | Documento de ideación |
| `research` | Mary | Reportes de investigación |
| `create-product-brief` | Mary | Product Brief |

### Fase 2: PLANNING (Requerida)

Define *qué* construir.

| Workflow | Agente | Salida |
|----------|--------|--------|
| `create-prd` | John (Product Manager) | PRD.md |
| `create-ux-design` | Sally (UX Designer) | UX Design.md |
| `quick-spec` | Amelia (Dev) | tech-spec.md |

### Fase 3: SOLUTIONING

Define *cómo* construir técnicamente.

| Workflow | Agente | Salida |
|----------|--------|--------|
| `create-architecture` | Winston (Architect) | Architecture.md |
| `create-epics-and-stories` | John (PM) | Epics & Stories.md |
| `check-implementation-readiness` | Winston | Readiness Report |

### Fase 4: IMPLEMENTATION

Construye story por story.

| Workflow | Agente | Descripción |
|----------|--------|-------------|
| `sprint-planning` | Bob (Scrum Master) | Inicializa sprint |
| `create-story` | Bob | Crea archivo de story |
| `dev-story` | Amelia (Developer) | Implementa tasks + tests |
| `code-review` | Amelia | Revisión adversarial |
| `retrospective` | Bob | Revisión post-epic |

---

## 4. Los 9 Agentes Especializados

Cada agente tiene una **persona única** y **expertise específico**:

### John - Product Manager
- **Archivo**: `src/bmm/agents/pm.agent.yaml`
- **Estilo**: "Pregunta 'POR QUÉ?' como detective"
- **Workflows**: Create PRD, Validate PRD, Edit PRD, Create Epics & Stories

### Amelia - Developer
- **Archivo**: `src/bmm/agents/dev.agent.yaml`
- **Estilo**: "Ultra-sucinto. Habla en rutas de archivos"
- **Workflows**: Dev Story, Code Review

### Winston - Architect
- **Archivo**: `src/bmm/agents/architect.agent.yaml`
- **Estilo**: "Tono calmado, pragmático"
- **Workflows**: Create Architecture, Implementation Readiness

### Mary - Business Analyst
- **Archivo**: `src/bmm/agents/analyst.agent.yaml`
- **Estilo**: "Entusiasta como cazador de tesoros"
- **Workflows**: Brainstorm, Research, Create Product Brief

### Bob - Scrum Master
- **Archivo**: `src/bmm/agents/sm.agent.yaml`
- **Estilo**: "Crispante y checklist-driven"
- **Workflows**: Sprint Planning, Create Story, Retrospective

### Sally - UX Designer
- **Archivo**: `src/bmm/agents/ux-designer.agent.yaml`
- **Estilo**: "Pinta cuadros con palabras"
- **Workflows**: Create UX Design

### Agentes Adicionales
- **quick-flow-solo-dev**: Para Quick Flow (features pequeñas)
- **tea**: Test Engineering Architecture
- **tech-writer**: Documentación técnica

---

## 5. Step File Architecture

BMAD utiliza una arquitectura disciplinada para workflows:

```
workflow.md (punto de entrada)
├── Metadata frontmatter
│   ├── name, description
│   ├── config_source
│   ├── nextStep (primer step)
│   └── web_bundle
│
└── Secuencia de steps
    ├── step-01-*.md
    ├── step-02-*.md
    └── step-XX-*.md
```

### Principios Core

1. **Micro-file Design**: Cada step es un archivo autónomo
2. **Just-In-Time Loading**: Solo carga el step actual
3. **Sequential Enforcement**: Ejecución en orden
4. **State Tracking**: Progreso en frontmatter
5. **Append-Only Building**: Construye agregando contenido

### Reglas Críticas

- NUNCA cargar múltiples step files simultáneamente
- SIEMPRE leer el step file completo antes de ejecutar
- NUNCA saltar steps
- SIEMPRE actualizar frontmatter al completar

---

## 6. Tecnologías Utilizadas

| Categoría | Tecnología |
|-----------|-----------|
| **Runtime** | Node.js ≥20.0.0 |
| **CLI** | Commander.js |
| **UI/Prompts** | @clack/prompts |
| **YAML** | js-yaml, yaml |
| **Markdown** | @kayvan/markdown-tree-parser |
| **Terminal UI** | chalk, boxen, cli-table3, figlet |
| **Documentación** | Astro + Starlight |
| **Validación** | Zod |
| **Testing** | Jest, c8 |
| **Linting** | ESLint, Prettier |
| **Git Hooks** | Husky, lint-staged |

---

## 7. Instalación y Uso

### Instalación

```bash
# Instalación automática (recomendada)
npx bmad-method install

# O instalación local
npm install bmad-method
npx bmad install
```

**Requisitos**:
- Node.js v20+
- Git (recomendado)
- IDE compatible: Claude Code, Cursor, Windsurf, Roo Code

### Dos Caminos de Uso

#### Quick Flow (Rápido)
Para bugs y features pequeñas:

```
1. /quick-spec      # Analiza código, produce tech-spec
2. /dev-story       # Implementa
3. /code-review     # Validación
```

#### BMad Method Completo
Para productos y features complejas:

```
# Análisis (opcional)
/brainstorm-project
/research
/create-product-brief

# Planificación
/create-prd
/create-ux-design

# Solutioning
/create-architecture
/create-epics-and-stories
/check-implementation-readiness

# Implementación (por cada epic)
/sprint-planning
/create-story epic-01 story-01
/dev-story path/to/story.md
/code-review path/to/story.md
/retrospective epic-01
```

---

## 8. Comandos CLI

```bash
# Instalación
npx bmad-method install          # Instalar BMAD

# Status
npx bmad status                   # Ver instalación actual

# Desarrollo
npm run lint                      # ESLint + YAML lint
npm run format:fix               # Prettier
npm run test                      # Tests completos
npm run validate:schemas         # Validar esquemas de agentes
npm run docs:dev                 # Dev mode documentación
npm run docs:build               # Build documentación
```

---

## 9. Party Mode

Permite traer múltiples agentes a una sesión:

```yaml
# src/bmm/teams/team-fullstack.yaml
bundle:
  name: Team Plan and Architect
  icon: "..."
  description: Team capable of project analysis, design, and architecture.
agents:
  - analyst
  - architect
  - pm
  - sm
  - ux-designer
```

---

## 10. Estructura de Archivos de Agentes

```yaml
# Formato: src/{module}/agents/{name}.agent.yaml
agent:
  metadata:
    id: "_bmad/{module}/agents/{name}.md"
    name: "Human Name"
    title: "Role Title"
    icon: "emoji"
    module: "module-code"

  persona:
    role: "Technical role description"
    identity: "Background and expertise"
    communication_style: "How they speak"
    principles: |
      - Principle 1
      - Principle 2

  critical_actions:
    - "Critical action 1"

  menu:
    - trigger: "AB or fuzzy match"
      workflow: "{project-root}/_bmad/...workflow.yaml"
      description: "[AB] Workflow Name"
```

---

## 11. Configuración del Proyecto

```yaml
# _bmad/config.yaml (generado al instalar)
code: bmm
name: "BMad Method Agile-AI Driven-Development"

user_name: "Your Name"
communication_language: "English"
document_output_language: "English"
output_folder: "_bmad-output"

project_name: "{directory_name}"
user_skill_level: "intermediate"  # beginner|intermediate|expert

planning_artifacts: "_bmad-output/planning-artifacts"
implementation_artifacts: "_bmad-output/implementation-artifacts"
project_knowledge: "docs"
```

---

## Resumen Ejecutivo

**BMAD-METHOD** es un framework de desarrollo impulsado por IA que proporciona:

- **9 agentes especializados** con expertise en cada rol
- **4 fases estructuradas** (Analysis → Planning → Solutioning → Implementation)
- **50+ workflows guiados** con step file architecture
- **Dos caminos**: Quick Flow (rápido) o BMad Method (completo)
- **Integración con IDEs** (Claude Code, Cursor, Windsurf)
- **100% Open Source** (MIT License)

El proyecto está activamente mantenido con documentación exhaustiva, tests automatizados (100% coverage), y una comunidad activa.

---

*Documento generado automáticamente mediante análisis del repositorio.*
