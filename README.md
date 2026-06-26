# VITALAB AUDIO · VLA-73 Mastering Analyzer

> Analizador de masterización **local, en un solo archivo HTML y sin dependencias**, con estética de hardware vintage tipo módulo Neve.
> Mide tu mezcla/máster, te da referencias por destino (streaming, CD, vinilo) y genera un informe PDF — todo en el navegador, sin subir tu audio a ningún sitio.

![single file](https://img.shields.io/badge/build-single--file_HTML-49e08a)
![dependencies](https://img.shields.io/badge/dependencies-0-blue)
![vanilla js](https://img.shields.io/badge/stack-vanilla_JS-ffae47)
![offline](https://img.shields.io/badge/offline-100%25-b23b30)

*Hecho para ti, no para todos.* — **Vitalab Audio**

---

## ¿Qué es?

VLA-73 es una herramienta **orientativa de pre-mastering**. Carga un archivo de audio y, en local, te muestra medidores analógicos en tiempo real, un análisis técnico completo del programa y recomendaciones de entrega para las principales plataformas. Está pensada como pieza de portfolio y laboratorio técnico, no como medidor certificado de estudio.

Todo el procesamiento ocurre en tu navegador con la **Web Audio API**. El audio nunca sale de tu equipo.

---

## Características

**Medición offline (sobre el archivo completo)**
- **Sample Peak** (dBFS)
- **RMS** (dBFS)
- **LUFS integrado** — K-weighting + gating según **ITU-R BS.1770-4** (coeficientes recalculados a la frecuencia de muestreo real)
- **LRA** (Loudness Range) según **EBU Tech 3342**
- **Correlación de fase** global y **correlación de graves (<150 Hz)** para compatibilidad de vinilo
- **PLR** (Peak-to-Loudness Ratio) y **factor de cresta**
- **DC offset** y **detección de clipping** por muestras consecutivas

**Medidores en tiempo real durante la reproducción**
- **VU de aguja** estilo Neve por canal (0 VU = −18 dBFS)
- **Aguja de correlación / fase**
- **Goniómetro** (Lissajous mid/side, fósforo verde)
- **Analizador de espectro** logarítmico (20 Hz – 20 kHz)
- **Espectro promedio offline** visible tras el análisis, sin necesidad de pulsar Play

**Recomendaciones por destino**
Referencias de loudness y techo true-peak, con el ajuste de ganancia exacto para acercarte a cada una:
CD (Red Book) · Spotify · Apple Music / iTunes · YouTube · Tidal / Amazon · Bandcamp / SoundCloud · Vinilo.

**Informe PDF**
Generador de PDF **propio, sin librerías externas** (texto Helvetica/WinAnsi, formas vectoriales y gráficos embebidos como JPEG/DCTDecode). Produce un informe de cliente/prensado con mediciones, diagnóstico, tabla de referencias y una página con el espectro promedio y el goniómetro.

---

## Cómo se usa

1. Abre `vitalab-audio-mastering.html` en un navegador moderno.
2. Pulsa **Cargar audio** y elige tu archivo.
3. Al terminar el análisis verás las métricas, el espectro promedio y las recomendaciones.
4. Pulsa **Play** para ver los medidores en movimiento (VU, fase, goniómetro, espectro).
5. Pulsa **Informe PDF** para descargar el informe.

Formatos recomendados: **WAV / AIFF** (decodificación segura en cualquier navegador). MP3 / M4A / FLAC dependen del soporte del navegador.

---

## Despliegue

Es un único archivo estático. No requiere build, servidor ni instalación.

- **Local:** doble clic sobre el `.html`.
- **GitHub Pages / Netlify / Vercel:** sube el archivo y listo. En Netlify basta con arrastrar la carpeta.

```
/
└── vitalab-audio-mastering.html   ← toda la app
└── README.md
```

---

## Tecnología

- **Vanilla JavaScript** — sin frameworks ni dependencias.
- **Web Audio API** — decodificación, reproducción y análisis.
- **Canvas 2D** — medidores, agujas y pantallas dibujados a mano.
- **FFT radix-2 propia** — para el espectro promedio offline.
- **Motor de PDF propio** — escribe el PDF a nivel de bytes (xref, objetos, streams), con fuentes estándar e imágenes DCTDecode.

Sin CDN, sin red, sin telemetría. Cero dependencias en `package.json` porque no hay `package.json`.

---

## Limitaciones (honestidad técnica)

VLA-73 es una guía técnica y musical, **no un sustituto de un medidor profesional certificado ni de una escucha crítica en entorno calibrado**.

- **Sample Peak, no True Peak.** El medidor de pico trabaja por muestra. El *true peak* real (inter-sample) requiere oversampling y está marcado como *pendiente* (fase 2). Los techos true-peak que ves son **recomendaciones de entrega**, no una medición interna.
- **Las referencias de loudness son orientativas**, no leyes. El objetivo es traducción, dinámica y ausencia de problemas técnicos, no perseguir un número.
- **Decodificación según navegador:** WAV/AIFF van seguros; otros formatos dependen del códec del navegador.
- **iOS / Safari:** la descarga del PDF puede abrir la hoja de compartir o una pestaña nueva en lugar de descargar directamente. Es comportamiento del sistema.
- **Análisis síncrono:** archivos muy largos pueden congelar la interfaz un instante (el paso a Web Worker está en el roadmap).

---

## Roadmap

| Versión | Objetivo | Incluye |
|---|---|---|
| **v1.1** ✅ | Corrección técnica y honestidad | LUFS mono correcto, Sample Peak separado de True Peak, espectro offline visible, PLR / crest / DC offset / clipping, textos honestos, aviso orientativo |
| v1.2 | Diagnóstico musical | Mejoras de informe, refinado de umbrales |
| v2.0 (DAM) | Arquitectura | Modularización, Web Worker (análisis no bloqueante), tests |
| Pro | Vitalab Audio | True Peak validado por oversampling, comparador A/B, presets, informes cliente/técnico |

---

## Sobre el proyecto

VLA-73 forma parte del ecosistema **Vitalab Audio** y de mi transición profesional hacia el desarrollo de software (DAM). Une conocimiento real de audio y criterio de mastering con programación web, construido de forma iterativa y validado de forma cruzada antes de cada cambio.

**Autor:** Sergio Devece — Vitalab Audio
**Diseño y desarrollo:** Designed by Sergio Devece_Vitalab Audio

---

## Licencia

© 2026 Sergio Devece · Vitalab Audio. Todos los derechos reservados.
