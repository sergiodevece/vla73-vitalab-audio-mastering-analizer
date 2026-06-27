# VITALAB AUDIO · VLA-73 Mastering Analyzer

**VLA-73 Mastering Analyzer** es una herramienta web de análisis orientativo de mezcla y mastering, creada dentro de la línea **Vitalab Audio**.

La aplicación permite cargar un archivo de audio, analizar métricas técnicas relevantes y visualizar medidores inspirados en hardware vintage de estudio, todo desde el navegador.

## Demo online

[Probar VLA-73 en Netlify](https://vla-73-mastering-vitalab-audio.netlify.app/)

## Qué es

VLA-73 es una herramienta de pre-mastering y revisión técnica. Está pensada como proyecto de portfolio, laboratorio de aprendizaje y puente entre experiencia profesional en audio y desarrollo web.

No pretende sustituir un sistema profesional certificado de medición ni una escucha crítica en sala calibrada. Su objetivo es ofrecer una guía visual y técnica útil para detectar posibles problemas y orientar decisiones de entrega.

## Funcionalidades principales

- Carga local de archivos de audio.
- Análisis técnico del archivo completo.
- Medición de Sample Peak, RMS y loudness integrado.
- Estimación de LRA, PLR y factor de cresta.
- Detección de DC offset y clipping.
- Correlación de fase global.
- Correlación de graves para orientación en vinilo.
- VU meters por canal con estética analógica.
- Goniómetro / visualizador estéreo.
- Analizador de espectro.
- Recomendaciones por destino de entrega.
- Generación de informe PDF.

## Demo y uso

1. Abre la [demo online](https://vla-73-mastering-vitalab-audio.netlify.app/).
2. Pulsa **Cargar audio**.
3. Selecciona un archivo compatible.
4. Revisa las métricas del análisis.
5. Usa la reproducción para ver los medidores en movimiento.
6. Genera el informe PDF si necesitas documentar la revisión.

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
└── vitalab-audio-mastering.html
```

`index.html` funciona como entrada estándar del proyecto.  
`vitalab-audio-mastering.html` conserva la aplicación principal completa.

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
- El comportamiento puede variar según navegador y formato de archivo.
- Archivos muy largos pueden requerir más tiempo de análisis.

## Roadmap

| Fase | Objetivo |
|---|---|
| v1 | Herramienta funcional de análisis y visualización |
| v1.1 | Correcciones técnicas, métricas más claras y documentación honesta |
| v1.2 | Mejoras de diagnóstico e informe |
| v2.0 | Modularización, Web Worker y tests durante DAM |
| Pro | True Peak avanzado, comparador A/B, presets e informes profesionales |

## Estado del proyecto

Proyecto funcional, desplegado online y en evolución.

## Autor

Proyecto creado por **Sergio Devece** dentro de **Vitalab Audio**.

© 2026 Sergio Devece · Vitalab Audio.
