# VITALAB AUDIO · VLA-73 Mastering Analyzer

**VLA-73 Mastering Analyzer** es una herramienta web de análisis orientativo de mezcla y mastering, creada dentro de la línea **Vitalab Audio**.

La aplicación permite cargar un archivo de audio, analizar métricas técnicas relevantes y visualizar medidores inspirados en hardware vintage de estudio, todo desde el navegador.

## Demo online

[DEMO · Probar VLA-73 v3 en Netlify](https://vla-73-mastering-vitalab-audio-v3.netlify.app/)

URL directa: https://vla-73-mastering-vitalab-audio-v3.netlify.app/

## Qué es

VLA-73 es una herramienta de pre-mastering y revisión técnica. Está pensada como proyecto de portfolio, laboratorio de aprendizaje y puente entre experiencia profesional en audio y desarrollo web.

No pretende sustituir un sistema profesional certificado de medición ni una escucha crítica en sala calibrada. Su objetivo es ofrecer una guía visual y técnica útil para detectar posibles problemas y orientar decisiones de entrega.

## Funcionalidades principales

- Carga local de archivos de audio.
- Análisis técnico del archivo completo.
- Medición de Sample Peak, RMS y loudness integrado.
- Detección automática de archivos mono/dual mono para evitar errores de medición LUFS por doble conteo de energía.
- Estimación de LRA, PLR y factor de cresta.
- Detección de DC offset y clipping.
- Correlación de fase global.
- Correlación de graves para orientación en vinilo.
- VU meters por canal con estética analógica.
- Goniómetro / visualizador estéreo.
- Analizador de espectro.
- Recomendaciones por destino de entrega.
- Escucha en mono para detectar cancelaciones de fase y problemas de compatibilidad.
- Generación de informe PDF.

## Demo y uso

1. Abre la [demo online v3](https://vla-73-mastering-vitalab-audio-v3.netlify.app/).
2. Pulsa **Cargar audio**.
3. Selecciona un archivo compatible.
4. Revisa las métricas del análisis.
5. Usa la reproducción para ver los medidores en movimiento.
6. Usa **Mono** para comprobar compatibilidad de fase.
7. Genera el informe PDF si necesitas documentar la revisión.

Formatos recomendados: **WAV** y **AIFF**. Otros formatos dependen del soporte del navegador.

## Tecnologías utilizadas

- HTML
- CSS
- JavaScript
- Web Audio API
- Canvas 2D
- Procesamiento de audio en navegador
- Generación de PDF desde JavaScript
- Netlify para despliegue online

## Estructura del proyecto

```txt
vla73-vitalab-audio-mastering-analizer/
├── README.md
├── index.html
├── vitalab-audio-mastering.html
├── vitalab-audio-mastering-v2.1.html
└── vitalab-audio-mastering-v3.html
```

- `index.html` funciona como entrada estándar del proyecto original.
- `vitalab-audio-mastering.html` conserva la aplicación principal completa de la primera versión publicada.
- `vitalab-audio-mastering-v2.1.html` conserva la iteración de estabilización previa.
- `vitalab-audio-mastering-v3.html` es la versión revisada, testada y promovida como referencia actual del proyecto.

## Versiones

El proyecto avanza en iteraciones pequeñas y verificables, conservando estética y estructura.

- **v1 / publicada original** — primera versión funcional de la herramienta.
- **v2.1 (estabilización)** — pasada de robustez sobre la máquina de estados, sin añadir features mayores:
  - Reset completo de estado al cargar un archivo nuevo o si falla la decodificación.
  - Botón Mono rehecho: comportamiento determinista desde parado, durante reproducción y tras pausa/stop.
  - Monitorado mono persistente tras Stop, como un botón de consola.
  - Ruta de salida de audio gobernada por el estado mono.
  - Detección de mono real por energía Side/Mid en lugar de solo correlación.
  - Corrección del cálculo LUFS en archivos mono/dual mono para evitar doble conteo de energía.
  - Mensajes coherentes entre interfaz e informe PDF: True Peak marcado como **N/A (fase 2)**.
- **v3 (actual)** — versión revisada y testada sobre Netlify, promovida como referencia funcional actual:
  - Mantiene la base robusta de v2.1.
  - Mejora legibilidad de recomendaciones y métricas.
  - Consolida el botón Mono dentro del flujo principal de uso.
  - Explicita la detección mono/dual mono y el cálculo LUFS corregido como parte del diagnóstico técnico.
  - Deja documentada la separación entre Sample Peak medido y True Peak pendiente de fase futura.
  - Mantiene enfoque local, estático y sin dependencias.

Esta v3 es una versión funcional de producto/laboratorio. La futura **v2.0 de arquitectura** del roadmap se refiere a modularización interna, Web Worker y tests durante DAM; no debe confundirse con la numeración de iteraciones funcionales ya publicadas.

## Enfoque Vitalab Audio

Este proyecto une dos mundos:

- experiencia real en producción, mezcla y mastering;
- aprendizaje y desarrollo de herramientas web.

La intención no es crear una app genérica de audio, sino una herramienta con criterio musical, estética propia y utilidad práctica dentro del ecosistema **Vitalab Audio**.

## Honestidad técnica

VLA-73 es una herramienta orientativa.

- No sustituye un medidor profesional certificado.
- Las referencias de loudness deben entenderse como guías, no como reglas absolutas.
- La medición de true peak validada por oversampling queda como mejora futura.
- Los techos true-peak indicados son recomendaciones de entrega, no medición interna de esta versión.
- El comportamiento puede variar según navegador y formato de archivo.
- Archivos muy largos pueden requerir más tiempo de análisis.

## Roadmap

| Fase | Objetivo |
| ---- | -------- |
| v1 | Herramienta funcional de análisis y visualización |
| v2.1 | Estabilización de estado, mono, LUFS mono/dual mono y PDF |
| v3 | Versión revisada/testada y referencia funcional actual |
| Arquitectura DAM | Modularización, Web Worker y tests durante DAM |
| Pro | True Peak avanzado, comparador A/B, presets e informes profesionales |

## Estado del proyecto

Proyecto funcional, desplegado online y en evolución. **VLA-73 v3** es la versión revisada y testada actualmente publicada en Netlify.

## Autor

Proyecto creado por **Sergio Devece** dentro de **Vitalab Audio**.

© 2026 Sergio Devece · Vitalab Audio.
