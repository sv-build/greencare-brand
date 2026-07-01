---
name: greencare-brand
description: Aplica la identidad visual de Green Care (Green Care del Perú) a CUALQUIER artefacto que generes — documentos, informes, presentaciones/slides, hojas de cálculo (Excel/Sheets), páginas HTML/landing/dashboards, correos, gráficos e imágenes. Define la paleta oficial (verde oscuro #296147, verde hoja #68AE2A, naranja #F3911D, crema #F0F2E5), la tipografía, el logo en SVG y las reglas de uso y contraste. Úsalo SIEMPRE que produzcas algo con la marca Green Care o para su equipo, aunque no digan "marca", "branding" ni "logo": basta con que el output sea de Green Care o vaya a llevar su imagen. También cuando pidan "ponle nuestros colores", "que se vea de la empresa", "con el logo", "estilo Green Care" o "formal para la gerencia".
---

# Green Care — marca visual

Skill para que cualquier cosa que generes salga con la identidad de **Green Care**: coherente,
legible y reconocible, sin importar el formato.

## Regla de oro (la marca en una línea)
Fondo claro de marca (crema o blanco), texto en **verde oscuro**, **verde hoja** como color
principal de detalles, **un** toque de **naranja** para resaltar lo importante, y el **logo**
según el fondo. Natural, limpio, con aire.

## Paleta (usar los roles, no el hex a mano)
- **Verde oscuro `#296147`** — títulos, texto sobre claro, fondos de secciones oscuras.
- **Verde hoja `#68AE2A`** — color principal de marca: íconos, fills, barras, detalles.
- **Naranja `#F3911D`** — acento: resaltar **un** dato clave, CTA. Escaso a propósito.
  "Una vista" = lo que se ve de un vistazo: una pantalla, una diapositiva o **una sección** de un
  documento. En un doc largo va **un naranja por sección**, no uno por documento entero.
- **Crema `#F0F2E5`** — fondo suave, alternativa cálida al blanco.
- Apoyo: blanco `#FFFFFF` (superficie), tinta `#22302A` (cuerpo de texto largo).

Los tokens listos para pegar están en **`assets/tokens.css`** (variables `--gc-*`).

### Dashboards y gráficos: usa la paleta funcional
Los 4 colores de marca son para **identidad**; se quedan cortos cuando hay que **distinguir muchos
datos** (series, categorías, estados). Para eso `tokens.css` incluye una **paleta funcional** —
categórica (`--gc-cat-1…8`), secuencial (`--gc-seq-*`), divergente (`--gc-div-*`), neutros
(`--gc-n-*`) y estados (`--gc-success/-warning/-danger/-info`). No inventes colores de marca nuevos
para gráficos: usa esta paleta. Cuándo va cada una → **`references/data-viz.md`**.

## Contraste (por qué importa)
Verde hoja y naranja **fallan como color de texto** sobre fondo claro (se vuelven ilegibles en
proyectores, pantallas malas y para baja visión). Son colores de **relleno/acento**, no de letra.
Para texto usa **verde oscuro o tinta sobre claro**, o **claro sobre verde oscuro**. Ratios y
combos seguros en **`references/tokens.md`**.

## Tipografía
**System font stack** (`--gc-font`): se ve nativa en cualquier equipo y carga al instante, sin
descargar fuentes — clave para docs y correos que se abren en cualquier lado. Jerarquía en
`references/tokens.md`.

## Esquinas: siempre redondeadas
La marca es orgánica (hojas, brotes); las esquinas rectas la endurecen. **Ningún elemento de UI
lleva esquinas a 90°.** Todo lo que tenga fondo, borde o imagen usa un radio de la escala:
- `--gc-radius-sm` (8px): inputs, chips, badges, celdas destacadas.
- `--gc-radius` (12px): botones y **tarjetas** (radio por defecto).
- `--gc-radius-lg` (20px): paneles grandes, modales, contenedores/hero.
- `--gc-radius-pill` (999px): botones pill, tags, avatares.

Aplica también a imágenes y contenedores de gráficos (`border-radius` + `overflow:hidden`). En
`references/artifacts.md` hay una **base de UI** lista para pegar que redondea botones, inputs,
tarjetas, tablas e imágenes de una vez.

## Logo (en `assets/`)
- `logo.svg` — lockup **apilado** (ícono arriba, wordmark abajo). Para usos centrados/verticales.
- `logo-horizontal.svg` — lockup **horizontal** (ícono izq. + wordmark der.). **Úsalo en encabezados
  y barras** (a poca altura el apilado queda ilegible).
- `logo-white.svg` — apilado en blanco, sobre fondo oscuro/foto.
- `logo-green-dark.svg` — una sola tinta (impresión, marca de agua).
- `mark.svg` — solo el ícono, `fill=currentColor`. Recolorea **solo si lo insertas inline** en el
  HTML (vía `<img>` el `currentColor` sale negro). Para `<img>` usa `mark-leaf.svg`.
- `mark-leaf.svg` — el ícono ya en verde hoja, listo para `<img>` (viñetas, favicon, watermark).
- `logo-hero.png` — render decorativo con glow para fondos oscuros; **no** es el logo funcional.

Reglas: respeta la zona de protección (≈ una hoja de margen), no deformes ni recolorees fuera de
las variantes, y elige la versión según el fondo. En espacios muy chicos usa solo el ícono
(`mark.svg`/`mark-leaf.svg`), no el lockup. Tamaños y detalle en `references/tokens.md`.

## Cómo aplicarla a cada artefacto
La marca es la misma; cambia el cómo. Abre **`references/artifacts.md`** para la receta concreta
de: HTML/landing/dashboard · documentos/informes · presentaciones · hojas de cálculo ·
imágenes/social · correos. Cada receta trae ejemplos y un checklist final.

## Antes de entregar, revisa
- Fondo claro de marca (o verde oscuro con texto claro).
- Texto con contraste suficiente (verde oscuro/tinta sobre claro).
- Verde hoja en detalles, no como texto pequeño.
- **Un** acento naranja por vista.
- Logo correcto para el fondo, con su zona de protección.
- Tipografía del sistema y jerarquía clara.
- **Esquinas redondeadas** en todo elemento de UI (nunca 90°).

> Este skill cubre lo **visual** (v1). Voz y tono de marca quedan para una versión futura.
