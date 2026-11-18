# Random 🎲

App web para hacer **selecciones aleatorias** a partir de subconjuntos de ítems definidos por el usuario, con reglas que deciden qué se considera, qué se excluye y cuánto pesa cada ítem antes de cada ronda.

**App:** https://luchorcompartidos.github.io/random/

## Cómo funciona

- **Subconjuntos:** grupos de ítems (por ejemplo "Cenas" o "Planes del finde"). Cada ítem tiene un **peso** (×1 por defecto) y **etiquetas** opcionales. Los subconjuntos también tienen peso, y tanto los ítems como los subconjuntos se pueden activar o desactivar.
- **Reglas** (se aplican antes de cada ronda):
  - **Excluir**: deja afuera los ítems alcanzados.
  - **Considerar solo**: participan únicamente los ítems alcanzados.
  - **Cambiar el peso**: multiplica las chances (×2 = el doble, ×0,5 = la mitad, ×0 = nunca).
  - **A quién aplican**: una etiqueta, un subconjunto, los ítems cuyo nombre contiene un texto, los que salieron en las últimas N rondas o los que nunca salieron.
- **Sorteo:** elegís cuántos ítems sacar, del total o de cada subconjunto, con o sin repetidos. Antes de sortear, la app muestra las **chances** de cada ítem y la lista de excluidos con el motivo.
- **Historial:** guarda cada ronda y alimenta las reglas de historial.
- **Datos:** se guardan en el navegador. Desde el menú ⋯ se pueden exportar e importar en `.json`.

El peso final de cada ítem es: peso del ítem × peso del subconjunto × reglas de peso. El sorteo sin repetidos usa el método de Efraimidis–Spirakis con números aleatorios de `crypto.getRandomValues`.

## Versiones

Sigue el estándar de la caja de apps (ver `luchorcompartidos/home` → `ESTANDAR-VERSIONES.md`): el número va en `<meta name="app-version">` y el tipo de Release se indica en el commit con `[major]`, `[minor]`, `[patch]` o `[skip release]`.
