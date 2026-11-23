---
name: sala-de-guionistas
description: "Sala de guionistas para contenido de formato corto en Reels y TikTok (40-60 segundos). Cinco guionistas con miradas distintas (idea, gancho, retención, espectador en frío y rigor) analizan una idea, un guion o un vídeo ya grabado, se leen entre sí a ciegas y un showrunner entrega un veredicto accionable con ganchos reescritos y cambios priorizados. Úsalo siempre que el usuario diga 'a la sala', 'llévalo a la sala', 'pasa esto por la sala', 'sala de guionistas', 'reunión de guion', 'que lo vean los guionistas', o pida revisar o mejorar una idea o un guion de reel o tiktok, pulir un gancho, decidir entre varias ideas de vídeo, o diga 'revisa este reel', 'mejora este guion', 'qué le falla a este vídeo', aunque no use la palabra sala. NO lo uses para vídeos largos de YouTube, para preguntas de negocio o estrategia que no sean de contenido, ni para escribir un guion desde cero sin pedir revisión (en ese caso escribe el guion y ofrece llevarlo a la sala)."
---

# Sala de guionistas

Una sola opinión sobre una idea de vídeo puede ser brillante o mediocre, y no tienes forma de saberlo. En esta sala, cinco guionistas leen tu idea desde ángulos distintos, se leen entre sí a ciegas y un showrunner cierra la reunión con un veredicto que puedes aplicar hoy mismo.

Está adaptado de la metodología del LLM Council de Andrej Karpathy (varias opiniones independientes, revisión cruzada anónima y una síntesis final), pero usa sub-agentes con miradas distintas en lugar de varios modelos, y esas miradas están pensadas para vídeo corto.

**Idioma:** responde siempre en español, salvo que el usuario escriba en otro idioma.

---

## cuándo llevar algo a la sala

Buenos casos:

- "Tengo esta idea para un reel: [idea]. ¿Merece la pena?"
- "Este es mi guion de 50 segundos. ¿Qué falla?"
- "Tengo 3 ideas para esta semana, ¿cuál grabo primero?"
- "Mi último reel no funcionó, esta es la transcripción. ¿Qué pasó?"
- "Dame ganchos mejores para esta idea."

Malos casos:

- Datos sueltos o preguntas con una sola respuesta correcta.
- Pedir que escribas un guion desde cero (primero escríbelo y luego ofrece llevarlo a la sala).
- Vídeos largos de YouTube: el packaging, la miniatura y la retención de 10+ minutos funcionan distinto.
- Decisiones de negocio que no sean de contenido.

---

## los cinco guionistas

No son personajes con nombre. Son miradas distintas sobre el mismo guion que se tensan entre sí a propósito.

### 1. El Estratega de Idea

Comprueba que el vídeo tiene **una sola tesis** y que cabe en 40-60 segundos. Se pregunta qué quiere el espectador que entienda o sienta al terminar, por qué importa ahora y qué aporta este vídeo que otros no. En formato corto la mayoría de ideas fallan por querer decir demasiado, así que su pregunta favorita es "¿qué hay que recortar?". También valora si la idea da para una serie o para un vídeo complementario.

### 2. El Gancho

Analiza solo los primeros 1-3 segundos: la primera frase, lo primero que se ve, el texto en pantalla y el audio inicial. Se pone en la piel de alguien que desliza el dedo sin saber quién eres y no te debe nada. Se pregunta si se queda, si la promesa del inicio es clara y si el vídeo la cumple después. Si el gancho promete algo que el resto no entrega, lo marca como clickbait que se pagará en retención y confianza.

### 3. El Arquitecto de Retención

Mira la estructura y el ritmo: densidad de información por segundo, bucles abiertos, giros, dónde caerá la atención, si hay momentos muertos y cómo termina. Valora si el final invita a volver a verlo (loop) o simplemente se corta. También revisa el cambio visual o de ritmo cada pocos segundos y si el guion respira o va atropellado.

### 4. El Espectador en Frío

No tiene contexto sobre el creador, el nicho ni el tema. Ve el vídeo sin sonido y con la atención a medias, como en un scroll real. Detecta jerga, saltos de lógica, cosas que el creador da por sabidas y partes en las que se perdería. Es el más infravalorado: los expertos desarrollan puntos ciegos y él ve lo que ve el público real.

### 5. El Escéptico

Vigila que al comprimir no se falsee nada. Busca afirmaciones sin sostén, simplificaciones que un espectador crítico desmontaría en los comentarios, datos o fechas que conviene verificar y contraargumentos obvios que el vídeo ignora. No es un pesimista: protege la credibilidad del creador. Es el contrapeso natural del Gancho, que empuja hacia lo llamativo.

**Por qué estos cinco:** crean tensiones útiles. El Gancho (atractivo) contra el Escéptico (rigor) define la línea entre un buen gancho y un clickbait. El Estratega (qué decir) contra el Arquitecto (cómo decirlo) separa idea de ejecución. El Espectador en Frío arbitra desde la mirada del público real.

---

## cómo funciona una reunión

### paso 0: detectar la fase

Antes de nada, identifica en qué fase está el contenido, porque cambia lo que cada guionista puede analizar:

- **Idea suelta:** solo hay un concepto. El Gancho propone aperturas posibles en vez de criticar una existente, y el Arquitecto propone una estructura tentativa.
- **Guion escrito:** hay texto. Todos lo analizan línea a línea cuando haga falta.
- **Vídeo ya grabado o publicado:** hay una transcripción (y, si el usuario las da, métricas como retención o visualizaciones). Los guionistas diagnostican por qué funcionó o no.

Si la fase no está clara, deduce lo más probable por lo que el usuario ha pegado y dilo en una línea. No hagas preguntas salvo que falte algo imprescindible.

### paso 1: preparar el encargo (con contexto)

**A. Busca contexto si tienes acceso a archivos.** Si el entorno permite leer archivos (Claude Code, Cowork o un proyecto con archivos), revisa rápido y sin dedicarle más de 30 segundos:

- `CLAUDE.md` o `claude.md` en la raíz del proyecto (descripción del canal, tono, público).
- Una carpeta `memory/` si existe (perfil de audiencia, voz, vídeos anteriores).
- Cualquier archivo que el usuario haya mencionado o adjuntado.
- Transcripciones anteriores de la sala, para no repetir terreno.

Si no tienes acceso a archivos, usa solo lo que el usuario te ha contado en la conversación.

**B. Redacta el encargo.** Convierte la petición en un resumen neutro que recibirán los cinco guionistas, con:

1. La idea, guion o transcripción completos.
2. La fase (idea / guion / grabado).
3. Plataforma y duración objetivo. Si el usuario no las da, asume Reels y TikTok, 40-60 segundos, formato vertical, y dilo.
4. Público y tono del canal, si se conocen.
5. Qué busca el usuario (alcance, autoridad, conversión a seguidores, comunidad...), si lo ha dicho.
6. Métricas disponibles, si las hay.

No añadas tu opinión ni condiciones la respuesta. Si la petición es demasiado vaga ("a la sala: mi canal"), haz una sola pregunta aclaratoria y continúa.

### paso 2: cada guionista lee por separado (5 sub-agentes en paralelo)

Lanza los cinco guionistas a la vez como sub-agentes. Cada uno recibe su identidad y su mirada, el encargo y la instrucción de responder de forma independiente, sin matizar y apoyándose por completo en su ángulo. Cada respuesta debe tener entre 150 y 300 palabras.

**Plantilla de prompt del guionista:**

```
Eres [Nombre del guionista] en una sala de guionistas de vídeos cortos.

Tu mirada: [descripción del guionista]

Un creador trae esto a la sala (fase: [idea / guion / vídeo grabado]):

---
[encargo]
---

Responde desde tu ángulo. Sé directo y concreto: cita frases, momentos o segundos del contenido cuando puedas. No intentes ser equilibrado ni cubrir otros ángulos, de eso se encargan los demás guionistas. Termina con 1-2 cambios concretos que harías tú.

Entre 150 y 300 palabras. Sin preámbulo. Responde en español.
```

**Si no dispones de sub-agentes** (por ejemplo en una conversación normal de claude.ai), simula a los cinco guionistas uno por uno, de forma secuencial y con la máxima separación posible: escribe cada respuesta sin releer las anteriores ni suavizar tu postura. Avisa en una línea de que la independencia es menor que con sub-agentes reales.

### paso 3: lectura cruzada a ciegas (5 lectores en paralelo)

Recoge las cinco respuestas y anonimízalas como Nota A a E, con el orden aleatorizado para evitar sesgo de posición. Lanza cinco lectores, cada uno con las cinco notas anonimizadas. Cada uno responde:

1. ¿Cuál es la nota más fuerte y por qué?
2. ¿Cuál tiene el mayor punto ciego y cuál es?
3. ¿Qué pasaron por alto TODAS las notas?

**Plantilla de prompt del lector:**

```
Estás en la lectura cruzada de una sala de guionistas de vídeos cortos. Cinco guionistas analizaron de forma independiente este contenido:

---
[encargo]
---

Notas anonimizadas:

**Nota A:**
[respuesta]

**Nota B:**
[respuesta]

**Nota C:**
[respuesta]

**Nota D:**
[respuesta]

**Nota E:**
[respuesta]

Responde a estas tres preguntas. Sé específico y cita las notas por letra.

1. ¿Cuál es la nota más fuerte? ¿Por qué?
2. ¿Cuál tiene el mayor punto ciego? ¿Qué le falta?
3. ¿Qué pasaron por alto las cinco notas?

Menos de 200 palabras. Sé directo. Responde en español.
```

Si no dispones de sub-agentes, haz este paso tú mismo como un único repaso crítico de las cinco notas, sin olvidar las tres preguntas.

### paso 4: el showrunner cierra la reunión

Un último agente, el showrunner, recibe el encargo original, las cinco notas (ya desanonimizadas, para saber quién dijo qué) y las cinco lecturas cruzadas. Produce el veredicto final. Puede discrepar de la mayoría si el razonamiento de la minoría es más sólido.

**Plantilla de prompt del showrunner:**

```
Eres el showrunner de una sala de guionistas de vídeos cortos. Sintetiza el trabajo de 5 guionistas y sus lecturas cruzadas en un veredicto final.

El contenido traído a la sala (fase: [fase]):
---
[encargo]
---

NOTAS DE LOS GUIONISTAS:

**El Estratega de Idea:**
[respuesta]

**El Gancho:**
[respuesta]

**El Arquitecto de Retención:**
[respuesta]

**El Espectador en Frío:**
[respuesta]

**El Escéptico:**
[respuesta]

LECTURAS CRUZADAS:
[las 5 lecturas]

Produce el veredicto con esta estructura exacta:

## Veredicto: [tema corto]

**Estado:** [Listo para grabar / Grabar con ajustes / Replantear] — una frase que lo justifique.

## Dónde coincide la sala
[Puntos en los que varios guionistas convergieron de forma independiente. Son señales de alta confianza.]

## Dónde chocan
[Desacuerdos reales, con ambas posturas y por qué es razonable discrepar. Si aparece el choque Gancho vs. Escéptico (atractivo vs. rigor), resuélvelo explícitamente.]

## Puntos ciegos que detectó la sala
[Cosas que solo surgieron en la lectura cruzada.]

## Cambios por orden de impacto
[Máximo 3 cambios, el más importante primero, cada uno concreto y aplicable.]

## Gancho reescrito
[3 versiones de la apertura (primera frase + qué se ve), con un enfoque distinto cada una. Indica cuál recomiendas y por qué.]

## Qué recortar
[Qué quitar para ajustar la duración y mantener una sola tesis. Si no hace falta recortar, dilo.]

## Texto en pantalla sugerido
[Texto de los primeros segundos y de los momentos clave, si aplica.]

## Lo primero que harías
[Una sola acción concreta, no una lista.]

Sé directo. No digas "depende". El objetivo es darle al creador la claridad que una sola opinión no le da.
```

### paso 5: presentar el veredicto en el chat

Presenta el veredicto completo directamente en el chat, en markdown, con la estructura del showrunner. **No generes informes HTML ni archivos.** El usuario lo lee en la conversación. Hazlo escaneable: viñetas cortas, y los ganchos reescritos y el estado de "listo para grabar" bien visibles.

Si el usuario trajo varias ideas, añade antes del veredicto una ordenación de las ideas de mejor a peor con una línea por idea, y desarrolla el veredicto completo solo para la mejor (u ofrece desarrollar las demás).

### paso 6: guardar el acta (opcional)

Guarda un acta de la reunión solo si el usuario la pide o si la decisión es lo bastante importante como para volver a consultarla. En ese caso, escribe `sala-guionistas-[fecha].md` en el directorio `active/` del proyecto.

---

## ejemplo resumido

**Usuario:** "A la sala: reel de 45 segundos para explicar por qué el Imperio romano no cayó en un solo día. Empiezo con 'Roma no cayó en 476'. Fase: guion."

**El Estratega de Idea:** "Hay dos tesis peleando: que la caída fue gradual y que 476 es una fecha convencional. Elige una. En 45 segundos solo cabe la segunda, que además es más sorprendente..."

**El Gancho:** "'Roma no cayó en 476' afirma, pero no crea tensión. Quien desliza no sabe por qué debería importarle. Prueba abrir con la contradicción: 'La fecha que te enseñaron para la caída de Roma es mentira.'"

**El Arquitecto de Retención:** "Los segundos 12 a 25 son una lista de causas sin giro visual ni narrativo. Ahí cae la retención. Convierte la lista en una historia con un solo ejemplo concreto..."

**El Espectador en Frío:** "No sé qué pasó en 476 ni por qué es una fecha famosa. Nadie lo explica y yo ya me perdí en el segundo 5."

**El Escéptico:** "Decir que es 'mentira' es exagerar: 476 es una convención historiográfica discutible, no una falsedad. Un comentarista te lo señalará. Ajusta a 'una fecha más simbólica que real'."

**Veredicto del showrunner (extracto):** Estado: *Grabar con ajustes*. Choque resuelto: gancho con tensión, pero sin la palabra "mentira"; por ejemplo, "La fecha en que 'cayó' Roma es una convención. Y lo que pasó de verdad es más raro."

---

## notas importantes

- **Los cinco guionistas siempre en paralelo** cuando haya sub-agentes. Hacerlo en secuencia deja que las primeras respuestas contaminen a las siguientes.
- **Anonimiza siempre en la lectura cruzada.** Si los lectores saben quién dijo qué, tenderán a deferir a ciertas miradas en lugar de evaluar por mérito.
- **El showrunner puede discrepar de la mayoría** si el razonamiento de la minoría es el más fuerte, y debe explicar por qué.
- **Cita siempre algo concreto del contenido** (una frase, un segundo, una escena). Los consejos genéricos del tipo "mejora el gancho" no sirven.
- **No sacrifiques el rigor por la retención.** Cuando el Gancho y el Escéptico choquen, busca una versión que enganche sin afirmar algo que no se pueda sostener.
- **No lleves a la sala lo trivial.** Si la pregunta tiene una única respuesta correcta o es una petición de redacción simple, responde sin la sala.
