# Random 🎲

App web para hacer **selecciones aleatorias** a partir de subconjuntos de ítems definidos por el usuario, con reglas que deciden qué se considera, qué se excluye y cuánto pesa cada ítem antes de cada ronda.

**App:** https://luchorcompartidos.github.io/random/

## Cómo funciona

- **Conjuntos:** el nivel superior. Cada conjunto es independiente y tiene sus propios subconjuntos, reglas, configuración de sorteo, historial y contador. Un sorteo usa solo el conjunto en uso: los conjuntos nunca se mezclan.
- **Subconjuntos:** grupos de ítems (por ejemplo "Cenas" o "Planes del finde"). Cada ítem tiene un **peso** (×1 por defecto) y **etiquetas** opcionales. Los subconjuntos también tienen peso, y tanto los ítems como los subconjuntos se pueden activar o desactivar.
- **Reglas** (se aplican antes de cada ronda):
  - **Excluir**: deja afuera los ítems alcanzados.
  - **Considerar solo**: participan únicamente los ítems alcanzados.
  - **Cambiar el peso**: multiplica las chances (×2 = el doble, ×0,5 = la mitad, ×0 = nunca).
  - **A quién aplican**: una etiqueta, un subconjunto, los ítems cuyo nombre contiene un texto, los que salieron en las últimas N rondas o los que nunca salieron.
- **Sorteo:** elegís cuántos ítems sacar, del total o de cada subconjunto, con o sin repetidos. Antes de sortear, la app muestra las **chances** de cada ítem y la lista de excluidos con el motivo.
- **Historial y contador:** guarda cada ronda y alimenta las reglas de historial. El contador 🎲 suma las veces que salió cada ítem, se puede reiniciar y después restaurar.
- **Orden:** conjuntos, subconjuntos e ítems se pueden ordenar a mano (arrastrando desde ⠿ o con ↑↓), por nombre, por peso, por cantidad de ítems, con los activos primero o por más o menos sorteados. Hay botones para contraer y expandir todo.
- **Tema:** Sistema, Claro u Oscuro, desde el menú ⋯.
- **Reiniciar sorteo:** deja el conjunto como recién creado para el sorteo (las reglas de historial empiezan de cero y el contador vuelve a 0) sin borrar el historial. Se puede deshacer.
- **Ocultar y archivar** (conjuntos, subconjuntos e ítems, cada uno por separado): ocultar lo saca de la vista y lo destilda; al mostrarlo de nuevo hay que volver a tildarlo para que participe. Archivar lo saca de todo (listas, sorteo, reglas) y lo guarda en «🗄 Archivados»; al desarchivarlo vuelve tal como estaba.
- **Copiar y mover:** desde ⋯ en cada ítem o subconjunto se puede duplicar, copiar o mover a otro subconjunto o conjunto. Con «☑ Seleccionar» se trabaja con varios ítems a la vez.
- **Planilla:** exportar e importar en Excel (.xlsx, con hojas Ítems, Conjuntos, Reglas e Historial) o CSV, y leer una Google Sheet publicada en la web (solo lectura). Al importar se puede actualizar por nombre, agregar como conjuntos nuevos o reemplazar todo. Lectura y escritura de .xlsx sin librerías externas.
- **Datos:** se guardan en el navegador. Desde el menú ⋯ hay respaldo completo en `.json`.

El peso final de cada ítem es: peso del ítem × peso del subconjunto × reglas de peso. El sorteo sin repetidos usa el método de Efraimidis–Spirakis con números aleatorios de `crypto.getRandomValues`.

## Versiones

Sigue el estándar de la caja de apps (ver `luchorcompartidos/home` → `ESTANDAR-VERSIONES.md`): el número va en `<meta name="app-version">` y el tipo de Release se indica en el commit con `[major]`, `[minor]`, `[patch]` o `[skip release]`.
