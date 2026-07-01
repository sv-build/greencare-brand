# Green Care — tokens de marca (detalle)

## Paleta

| Rol | Nombre | HEX | Uso |
|-----|--------|-----|-----|
| `--gc-green-dark` | Verde oscuro | `#296147` | Títulos, texto sobre claro, fondos de secciones oscuras |
| `--gc-green-leaf` | Verde hoja | `#68AE2A` | Color principal de marca: fills, íconos, barras, detalles |
| `--gc-orange` | Naranja | `#F3911D` | Acento: resaltar **un** dato clave, CTA, subrayado |
| `--gc-cream` | Crema | `#F0F2E5` | Fondo suave (alternativa cálida al blanco) |
| `--gc-white` | Blanco | `#FFFFFF` | Superficie base |
| `--gc-ink` | Tinta | `#22302A` | Texto de cuerpo largo sobre fondo claro |

Neutros derivados (para bordes/estados), si necesitas grises los tomas del verde:
mezcla verde oscuro con blanco (ej. bordes suaves `rgba(41,97,71,.15)`).

## Contraste y legibilidad (accesibilidad)

Esto importa porque el texto poco contrastado se vuelve ilegible en pantallas malas,
proyectores y para personas con baja visión — y arruina la percepción de la marca.
Ratios calculados contra WCAG (AA para texto normal = 4.5:1; large ≥ 3:1).

**Combinaciones seguras para texto**
- Verde oscuro `#296147` sobre crema `#F0F2E5` → **6.4:1** ✔ AA
- Verde oscuro `#296147` sobre blanco → **7.3:1** ✔ AAA
- Tinta `#22302A` sobre crema/blanco → altísimo ✔ (cuerpo largo)
- Blanco o crema sobre verde oscuro `#296147` → **~7:1** ✔ (secciones oscuras)

**NO usar como color de texto sobre fondo claro** (fallan contraste):
- Verde hoja `#68AE2A` sobre blanco → 2.7:1 ✘
- Naranja `#F3911D` sobre blanco → 2.4:1 ✘
- Blanco pequeño sobre verde hoja o naranja → ✘

Regla práctica: **verde hoja y naranja son colores de _relleno/acento_, no de texto.**
Si necesitas texto encima de ellos, usa piezas grandes (≥24px, bold) y tinta/verde oscuro
como color de letra, nunca cuerpo pequeño.

## El acento naranja: uno por vista

El naranja es el color que rompe. Su fuerza viene de la escasez: **un solo elemento naranja
por pantalla/diapositiva/sección** (el dato que quieres que recuerden, el CTA, el número clave).
Si todo es naranja, nada resalta.

## Tipografía

- Familia: **system font stack** (`--gc-font`). Se ve nativa en cada equipo, carga al instante
  y no depende de descargar fuentes — importante para docs y correos que se abren en cualquier lado.
- Jerarquía sugerida:
  - Display/H1: 40–56px, `font-weight:800`, `letter-spacing:-.01em`, color verde oscuro.
  - H2: 28–32px, 700.
  - H3: 20–22px, 700.
  - Cuerpo: 16–18px, 400, `line-height:1.6`, color tinta.
  - Etiquetas/overline: 12–13px, 700, `text-transform:uppercase`, `letter-spacing:.08em`, verde hoja.
- El wordmark del logo usa mayúsculas con tracking ligero; no lo reemplaces por otra fuente.

## Forma y ritmo

**Esquinas: siempre redondeadas** (la marca es orgánica; las esquinas rectas la endurecen).
Ningún elemento de UI a 90°. Escala de radios:

| Token | Valor | Para |
|-------|-------|------|
| `--gc-radius-sm` | 8px | inputs, chips, badges, celdas |
| `--gc-radius` | 12px | botones, **tarjetas** (por defecto) |
| `--gc-radius-lg` | 20px | paneles grandes, modales, hero |
| `--gc-radius-pill` | 999px | botones pill, tags, avatares |

- Aplica a imágenes y contenedores de gráficos (`border-radius` + `overflow:hidden`).
- Espaciado en múltiplos de 8 (`--gc-space`): 8 / 16 / 24 / 32 / 48.
- Sombra sutil verdosa `--gc-shadow` en tarjetas; evitar sombras grises neutras.

## Logo — archivos y uso

| Archivo | Cuándo |
|---------|--------|
| `assets/logo.svg` | Primario, sobre fondo claro (crema/blanco). Hojas verde hoja + wordmark verde oscuro. |
| `assets/logo-white.svg` | Sobre fondo oscuro, foto o el verde oscuro de marca. |
| `assets/logo-green-dark.svg` | Una sola tinta sobre fondo claro (impresión, sellos, marca de agua). |
| `assets/mark.svg` | Solo el ícono (3 hojas), `fill=currentColor`: favicon, avatar, viñetas, watermark. Recolorea con `color:` en CSS. |
| `assets/logo-hero.png` | Render decorativo con glow para fondos/hero oscuros. No usar como logo funcional sobre claro. |

**Reglas de uso**
- Zona de protección: deja alrededor un margen ≥ la altura de una hoja del ícono.
- Tamaño mínimo legible del lockup completo: ~120px de ancho; por debajo, usa solo `mark.svg`.
- No deformes, rotes, ni cambies los colores fuera de las variantes provistas.
- No pongas `logo.svg` (versión clara) sobre fondos oscuros; ahí va `logo-white.svg`.

> Nota: el logo SVG es una **reconstrucción limpia y escalable** del mark. Si Green Care
> entrega el archivo vectorial oficial, reemplaza los `.svg` de `assets/` conservando los nombres.
