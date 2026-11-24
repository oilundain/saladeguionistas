# Sala de guionistas

Un skill de Claude para mejorar vídeos de formato corto (Reels y TikTok, 40-60 segundos). Llevas una idea, un guion o un vídeo ya grabado a la sala: cinco guionistas lo leen desde ángulos distintos, se leen entre sí a ciegas y un showrunner cierra la reunión con un veredicto que puedes aplicar hoy.

## Los cinco guionistas

1. **El Estratega de Idea:** una sola tesis y qué recortar.
2. **El Gancho:** los primeros 1-3 segundos.
3. **El Arquitecto de Retención:** ritmo, bucles abiertos y final.
4. **El Espectador en Frío:** la mirada sin contexto, como en un scroll real.
5. **El Escéptico:** rigor y credibilidad al comprimir.

Se tensan a propósito: el Gancho (atractivo) contra el Escéptico (rigor), y el Estratega (qué decir) contra el Arquitecto (cómo decirlo).

## Qué entrega

- Estado: listo para grabar, grabar con ajustes o replantear.
- Los 3 cambios más importantes, por orden de impacto.
- 3 ganchos reescritos.
- Qué recortar para ajustar la duración.
- Texto en pantalla sugerido.
- Una única acción inmediata.

Funciona con una idea suelta, un guion escrito o la transcripción de un vídeo ya publicado.

## Cómo instalarlo (sin terminal)

**Opción 1: que Claude lo instale por ti.** Abre una conversación nueva en Claude y pega esto, cambiando la URL por la de este repositorio:

> Instala este skill de Claude por mí. El archivo SKILL.md está en este repositorio de GitHub: https://github.com/oilundain/saladeguionistas
> Déjalo listo para usarlo y guíame en lo que necesites.

**Opción 2: descarga el archivo.**
1. Abre [SKILL.md](SKILL.md) y descárgalo.
2. Pégalo en una conversación con Claude y pídele que lo instale, o en Ajustes → Capacidades → Skills súbelo como `.zip` de una carpeta llamada `sala-de-guionistas` que contenga el `SKILL.md`.

## Cómo usarlo

Dile a Claude cosas como:

- "A la sala: [tu idea o guion]"
- "Llévalo a la sala"
- "Pasa esto por la sala de guionistas"
- "Revisa este reel" o "mejora este guion"

Para mejores resultados indica la fase (idea, guion o ya grabado) y, si la tienes, la transcripción y las métricas.

> En Claude Code y Cowork lanza a los guionistas como sub-agentes en paralelo. En una conversación normal de claude.ai, Claude los simula uno por uno, con algo menos de independencia.

## Créditos

Adaptado del skill [LLM Council](https://github.com/aiwithremy/claude-skills-llm-council) de Ole Lehmann, que a su vez se basa en la metodología [LLM Council](https://github.com/karpathy/llm-council) de Andrej Karpathy. Esta versión sustituye los cinco advisors genéricos por cinco guionistas especializados en vídeo corto.
