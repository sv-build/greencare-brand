# Colores para datos, gráficos y dashboards

## Por qué existe esta paleta aparte
La **paleta de marca** (verde oscuro, verde hoja, naranja, crema) sirve para la **identidad**:
pocos colores, memorables. Es perfecta para un logo, una portada o una landing, pero se queda
corta cuando necesitas **distinguir muchos datos** (6 series en un gráfico, categorías, estados).
Por eso hay una **paleta funcional** (`--gc-cat-*`, `--gc-seq-*`, `--gc-div-*`, neutros, estados)
que **deriva de la marca pero existe para diferenciar**, no para representar la marca.

Regla mental: **marca = identidad (pocos), datos = función (muchos, distinguibles).**
No inventes colores de marca nuevos; para gráficos usa esta paleta funcional.

## Cuál usar según el tipo de dato

| Tipo de dato | Paleta | Tokens |
|--------------|--------|--------|
| Categorías / series distintas (barras, pie, líneas) | Categórica | `--gc-cat-1 … --gc-cat-8` (en orden) |
| Intensidad de **un** dato (heatmap, mapa, densidad) | Secuencial | `--gc-seq-1 … --gc-seq-5` (claro→oscuro) |
| Datos con signo / desvío de un punto medio (+/-) | Divergente | `--gc-div-neg2 … --gc-div-pos2` |
| Ejes, grillas, bordes, texto secundario | Neutros | `--gc-n-50 … --gc-n-900` |
| Estados (OK / alerta / error / info) | Estados | `--gc-success`, `--gc-warning`, `--gc-danger`, `--gc-info` (+ `-bg`) |

## Reglas de uso

- **Orden categórico**: usa `--gc-cat-1` primero y baja en orden. Los primeros están pensados para
  ser los más distinguibles entre sí; si solo tienes 3 series, usarás 1/2/3 y ya se ven separadas.
- **Destaca una serie**: deja las demás en un neutro (`--gc-n-400`) y pinta la protagonista con
  `--gc-cat-1` o `--gc-accent`. Un dashboard no necesita que TODO tenga color; el color guía la vista.
- **Secuencial ≠ categórico**: no uses tonos del mismo verde para categorías distintas (se leen como
  "más/menos", no como "A/B/C"). Para categorías, hues diferentes; para intensidad, un solo hue.
- **Grillas y ejes**: `--gc-n-200`/`--gc-n-400`, nunca negro puro — compite con los datos.
- **Fondo del dashboard**: crema (`--gc-surface-soft`) o blanco; tarjetas blancas con `--gc-shadow`.

## Accesibilidad (por qué importa en dashboards)
Un dashboard se lee en proyectores, laptops con brillo bajo y por gente con daltonismo; si dos
series se distinguen solo por un matiz parecido, el dato se pierde.
- La categórica alterna cálidos y fríos (verde/teal/naranja/dorado/azul…) justamente para que sean
  distinguibles incluso en daltonismo común. Aun así, **no dependas solo del color**: agrega
  etiquetas, íconos o patrones a las series críticas.
- **Colores de texto** (KPIs, estados): `--gc-success`, `--gc-danger`, `--gc-info` tienen contraste
  suficiente sobre blanco. **`--gc-warning` (naranja) NO** — para texto de alerta usa `--gc-n-900`
  sobre `--gc-warning-bg`. El naranja va como fill/ícono, no como letra pequeña.

## Ejemplos

**Chart.js / cualquier lib que reciba un array de colores** (léelo del CSS o cópialos):
```js
const GC_CATEGORICAL = ['#68AE2A','#2A9D8F','#F3911D','#E9C46A','#3A7CA5','#C1542C','#7A6C9B','#4C6B54'];
```

**KPI con estado (HTML):**
```html
<div class="kpi">
  <span class="num" style="color:var(--gc-brand-deep)">S/ 128k</span>
  <span class="chip" style="color:var(--gc-success);background:var(--gc-success-bg)">▲ 12%</span>
</div>
```

**Barras destacando una (CSS):**
```css
.bar        { background: var(--gc-n-200); }   /* contexto, apagado */
.bar.is-key { background: var(--gc-cat-1); }   /* la que importa */
```
