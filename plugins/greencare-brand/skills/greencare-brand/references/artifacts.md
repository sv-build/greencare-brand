# Recetas por artefacto

El skill es agnóstico al artefacto: la marca es la misma, cambia cómo se aplica.
En todos los casos: fondo claro (crema/blanco), texto verde oscuro/tinta, verde hoja para
detalles, **un** acento naranja por vista, logo según fondo. Detalle de tokens y contraste en
`tokens.md`.

## Base de UI (pegar una vez, redondea todo)
Después de `tokens.css`, pega esta base: aplica las esquinas redondeadas de marca a los elementos
de UI comunes para no repetir `border-radius` en cada uno.

```css
button, .btn, input, select, textarea, .chip, .badge { border-radius: var(--gc-radius-sm); }
.card, .panel, .btn-lg { border-radius: var(--gc-radius); }
.modal, .hero, .container-rounded { border-radius: var(--gc-radius-lg); }
.pill, .tag, .avatar { border-radius: var(--gc-radius-pill); }
img, .chart, table, figure { border-radius: var(--gc-radius); overflow: hidden; }
```

## HTML / landing / dashboard
- Pega `assets/tokens.css` y usa las variables `--gc-*` (nunca el hex crudo).
- Esquinas redondeadas en todo (ver "Base de UI" arriba); nunca elementos a 90°.
- Estructura típica:
  - Header con `logo.svg` (alto ~32–40px) sobre crema/blanco.
  - Títulos verde oscuro; cuerpo tinta; links verde hoja con subrayado en hover.
  - Tarjetas: fondo blanco, `border-radius:var(--gc-radius)`, `box-shadow:var(--gc-shadow)`.
  - Un botón/dato clave en naranja (`background:var(--gc-accent)`, texto verde oscuro o blanco grande).
  - Secciones oscuras: `background:var(--gc-brand-deep)`, texto crema, `logo-white.svg`.
- Íconos: usa `mark.svg` con `color:` para viñetas o watermark sutil.

```html
<link rel="stylesheet" href="assets/tokens.css">
<header style="background:var(--gc-surface-soft);padding:16px 24px">
  <img src="assets/logo.svg" alt="Green Care" height="36">
</header>
<h1 style="font:800 48px/1.1 var(--gc-font);color:var(--gc-brand-deep)">Título</h1>
<p style="font:400 17px/1.6 var(--gc-font);color:var(--gc-text)">Cuerpo…</p>
<span style="background:var(--gc-accent);color:var(--gc-brand-deep);
  font-weight:800;padding:4px 10px;border-radius:var(--gc-radius-sm)">dato clave</span>
```

## Documentos / informes (Markdown, Word, Google Docs, PDF)
- Portada: fondo crema o verde oscuro con `logo` (variante según fondo), título grande.
- Encabezados en verde oscuro; texto en tinta; interlineado 1.5–1.6.
- Resalta cifras/hallazgos clave con un fondo o texto naranja — con moderación.
- Viñetas con el ícono de hoja (`mark.svg`) o un guión simple.
- Pie de página con el `mark.svg` pequeño + "Green Care".
- Al exportar a PDF, usa la paleta como colores de estilo, no capturas de pantalla.

## Presentaciones / slides
- Plantilla base: fondo crema; barra o filete superior verde hoja.
- Portada y cierre: fondo verde oscuro + `logo-white.svg` centrado.
- Un color de énfasis por slide (naranja) para el número/mensaje que debe quedar.
- Títulos verde oscuro 32–40px; bullets cortos en tinta; gráficos en verde hoja con
  una serie destacada en naranja.
- No mezclar más de 2 colores de marca en un mismo gráfico + el acento.

## Hojas de cálculo (Excel / Google Sheets)
- Encabezados de tabla: fondo verde oscuro, texto blanco/crema, negrita.
- Filas alternas: blanco / crema (`#F0F2E5`) para zebra suave.
- Totales o KPI destacado: fondo naranja con texto verde oscuro (grande/negrita), uno por vista.
- Verde hoja para barras de datos, formato condicional positivo, mini-charts.
- Bordes finos en `rgba(41,97,71,.15)`, no negro puro.

## Imágenes / social / gráficos
- Fondo crema o verde oscuro; el `mark.svg` como watermark en esquina (baja opacidad).
- Paleta limitada: verde hoja como protagonista, naranja solo en el foco.
- Si generas imágenes con IA: pide fondo sólido de marca, sin texto incrustado (el texto se
  compone encima con la tipografía), acentos en naranja, estética natural/orgánica (hojas, brotes).
- Exporta a la cascada web (AVIF+WebP+JPEG) cuando sea para web.

## Correos
- Texto plano o HTML simple: título verde oscuro, cuerpo tinta, un enlace/CTA.
- Firma con `mark.svg` o `logo.svg` pequeño (≤160px). Evita fondos oscuros en el cuerpo del correo
  (muchos clientes los rompen); reserva el verde oscuro para la firma/encabezado.

## Checklist rápido (aplica a cualquier artefacto)
- [ ] Fondo claro de marca (crema/blanco) o verde oscuro con texto claro.
- [ ] Texto legible: verde oscuro/tinta sobre claro (ver contraste en `tokens.md`).
- [ ] Verde hoja como color principal de detalles, no como texto pequeño.
- [ ] **Un** acento naranja por vista.
- [ ] Logo correcto según el fondo, con zona de protección.
- [ ] Tipografía = system font stack, jerarquía clara.
