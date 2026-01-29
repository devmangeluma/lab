## Protocolo de Orquestación de Discusión - Party Mode

El **Party Mode** es un workflow del método BMAD que orquesta conversaciones grupales entre múltiples agentes de IA. Funciona así:

### Arquitectura General

Usa una **arquitectura de micro-archivos** con orquestación secuencial:
- **Step 01**: Carga el manifiesto de agentes e inicializa el modo
- **Step 02**: Orquesta la discusión multi-agente continua
- **Step 03**: Maneja la salida elegante del modo

### Flujo de Funcionamiento

#### 1. Inicialización
- Carga configuración desde `_bmad/core/config.yaml`
- Lee el manifiesto de agentes (`agent-manifest.csv`) que contiene:
  - Nombre, título, icono, rol
  - Identidad/expertise del agente
  - Estilo de comunicación
  - Principios de decisión

#### 2. Selección Inteligente de Agentes
Para cada mensaje del usuario:
- **Análisis de entrada**: Determina qué expertise se necesita
- **Selección de 2-3 agentes**:
  - **Primario**: Mejor match de expertise
  - **Secundario**: Perspectiva complementaria
  - **Terciario**: Insight cross-domain o "abogado del diablo"

#### 3. Orquestación de Conversación
- **Consistencia de personaje**: Cada agente mantiene su estilo de comunicación único
- **Cross-talk natural**: Los agentes pueden referenciarse entre sí ("Como mencionó [Agente X]...")
- **Manejo de preguntas**:
  - Si un agente pregunta al usuario → Pausa y espera respuesta
  - Preguntas entre agentes → Continúan en la misma ronda

#### 4. Control de Flujo
- Rotación de agentes para participación inclusiva
- Si la discusión se vuelve circular, el agente maestro redirige
- Balance entre diversión y productividad

### Condiciones de Salida
- Triggers automáticos: `*exit`, `goodbye`, `end party`, `quit`
- El usuario puede seleccionar `[E] Exit Party Mode` después de cada ronda
- Despedidas personalizadas de cada agente al terminar

### Ejemplo de Estructura de Respuesta
```
🎯 Analizando tu mensaje para la colaboración perfecta...

[Emoji] **Agente 1**: [Respuesta en su estilo único]

[Emoji] **Agente 2**: [Perspectiva complementaria]

[E] Exit Party Mode - Finalizar la sesión colaborativa
```

¿Tienes alguna pregunta específica sobre algún aspecto del protocolo?
