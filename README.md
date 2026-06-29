# VITALAB AUDIO · VLA-73 Mastering Analyzer

**VLA-73 Mastering Analyzer** es una herramienta web de análisis orientativo de mezcla y mastering, creada dentro de la línea **Vitalab Audio**.

La aplicación permite cargar un archivo de audio, analizar métricas técnicas relevantes y visualizar medidores inspirados en hardware vintage de estudio, todo desde el navegador.

![static app](https://img.shields.io/badge/build-static_app-49e08a)
![dependencies](https://img.shields.io/badge/dependencies-0-blue)
![vanilla js](https://img.shields.io/badge/stack-vanilla_JS-ffae47)
![web audio](https://img.shields.io/badge/audio-Web_Audio_API-b23b30)
![status](https://img.shields.io/badge/status-v2_stable-8b5cf6)

*Hecho para ti, no para todos.* — **Vitalab Audio**

---

## Demo online

[Probar VLA-73 en Netlify](https://vla-73-mastering-vitalab-audio.netlify.app/)

---

## Qué es

**VLA-73** es una herramienta de **pre-mastering y revisión técnica**. Está pensada como proyecto de portfolio, laboratorio de aprendizaje y puente entre experiencia profesional en audio y desarrollo web.

No pretende sustituir un sistema profesional certificado de medición ni una escucha crítica en sala calibrada. Su objetivo es ofrecer una guía visual y técnica útil para detectar posibles problemas y orientar decisiones de entrega.

Todo el análisis se realiza localmente en el navegador. La app no sube el audio a ningún servidor.

---

## Funcionalidades principales

- Carga local de archivos de audio.
- Análisis técnico del archivo completo.
- Medición de **Sample Peak**, **RMS** y **LUFS integrado**.
- Estimación de **LRA**, **PLR** y **factor de cresta**.
- Detección de **DC offset** y clipping por muestras.
- Correlación de fase global.
- Correlación de graves para orientación en vinilo.
- VU meters por canal con estética analógica.
- Goniómetro / visualizador estéreo.
- Analizador de espectro promedio.
- Recomendaciones por destino de entrega.
- Botón de escucha en mono para revisar compatibilidad.
- Generación de informe PDF.

---

## Novedades de VLA-73 v2

La versión **v2** consolida la herramienta como una iteración funcional más estable, honesta y técnicamente clara.

### Correcciones y mejoras principales

- Corrección del cálculo de LUFS en archivos mono y dual mono.
- Detección de mono más robusta mediante energía **Side/Mid**, evitando falsos positivos por correlación alta.
- Separación explícita entre **Sample Peak** y **True Peak**.
- True Peak marcado como `N/A / fase 2` hasta implementar oversampling.
- Reset limpio al cargar un nuevo archivo o si falla la decodificación.
- Botón **Mono** corregido y persistente, con comportamiento tipo consola.
- Ruta de audio mono más robusta, sin duplicar salida ni sumar +6 dB accidentalmente.
- Restauración del espectro promedio al detener reproducción.
- Informe PDF actualizado con métricas más claras.
- Textos técnicos revisados para evitar falsa precisión.
- Recomendaciones de entrega separadas de la medición interna real.

### Estado técnico de v2

- **Sample Peak:** medición directa de pico de muestra.
- **True Peak:** no medido todavía; previsto para fase futura con oversampling/FIR.
- **LUFS integrado:** cálculo orientativo basado en K-weighting y gating.
- **Mono / dual mono:** detección mediante canal único, diferencia L/R y energía Side/Mid.
- **PDF:** informe local generado desde JavaScript, sin dependencias externas.

---

## Demo y uso

1. Abre la [demo online](https://vla-73-mastering-vitalab-audio.netlify.app/).
2. Pulsa **Cargar audio**.
3. Selecciona un archivo compatible.
4. Revisa las métricas del análisis.
5. Usa la reproducción para ver los medidores en movimiento.
6. Activa **Mono** para comprobar compatibilidad de fase.
7. Genera el informe PDF si necesitas documentar la revisión.

Formatos recomendados: **WAV** y **AIFF**. Otros formatos dependen del soporte del navegador.

---

## Tecnologías utilizadas

- HTML5
- CSS3
- JavaScript vanilla
- Web Audio API
- Canvas 2D
- Procesamiento de audio en navegador
- Generación de PDF desde JavaScript
- Netlify para despliegue online

No requiere instalación, compilación, backend ni dependencias externas.

---

## Estructura del proyecto

```txt
vla73-vitalab-audio-mastering-analizer/
├── README.md
├── index.html
└── vitalab-audio-mastering.html
```

`index.html` funciona como entrada estándar del proyecto.  
`vitalab-audio-mastering.html` conserva la aplicación principal completa.

---

## Enfoque Vitalab Audio

Este proyecto une dos mundos:

- experiencia real en producción, mezcla y mastering;
- aprendizaje y desarrollo de herramientas web.

La intención no es crear una app genérica de audio, sino una herramienta con criterio musical, estética propia y utilidad práctica dentro del ecosistema **Vitalab Audio**.

VLA-73 forma parte del camino de aprendizaje técnico hacia desarrollo de software, IA aplicada y formación DAM, aprovechando la experiencia musical acumulada como base real de producto.

---

## Honestidad técnica

VLA-73 es una herramienta **orientativa** de pre-mastering.

- No sustituye un medidor profesional certificado.
- No sustituye una escucha crítica en entorno calibrado.
- Las referencias de loudness deben entenderse como guías, no como reglas absolutas.
- La medición de True Peak validada por oversampling queda como mejora futura.
- Los techos de entrega como `−1 dBTP` son recomendaciones de industria, no una medición interna de esta versión.
- El comportamiento puede variar según navegador y formato de archivo.
- Archivos muy largos pueden requerir más tiempo de análisis.

---

## Roadmap

| Fase | Objetivo | Estado |
|---|---|---|
| v1 | Herramienta funcional de análisis y visualización | ✅ Completada |
| v1.1 | Correcciones técnicas, métricas más claras y documentación honesta | ✅ Integrada |
| v1.2 | Mejoras de diagnóstico e informe | ✅ Integrada |
| v2 | Estabilidad, mono/LUFS corregido, PDF actualizado y ruta mono robusta | ✅ Actual |
| v2.1 | Pulido fino de UX, rendimiento y validación cruzada | Próxima |
| v3 | Modularización, Web Worker y tests durante DAM | Futuro |
| Pro | True Peak avanzado, comparador A/B, presets e informes profesionales | Futuro |

---

## Estado del proyecto

**VLA-73 Mastering Analyzer v2** está publicado como versión funcional estable.

Estado actual:

- App funcional.
- Proyecto estático sin dependencias.
- Código principal en `vitalab-audio-mastering.html`.
- Demo online desplegada en Netlify.
- Informe PDF integrado.
- Preparado como pieza de portfolio y laboratorio Vitalab Audio.

---

## Autor

Proyecto creado por **Sergio Devece** dentro de **Vitalab Audio**.

**Diseño, concepto y desarrollo:** Sergio Devece · Vitalab Audio

---

## Licencia

© 2026 Sergio Devece · Vitalab Audio. Todos los derechos reservados.

Este proyecto forma parte de un proceso personal de aprendizaje, portfolio y desarrollo de herramientas propias.
