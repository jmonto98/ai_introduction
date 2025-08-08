# Algoritmo A* para encontrar la ruta óptima a Bucarest

## Análisis del problema

El problema consiste en encontrar la ruta óptima desde Arad hasta Bucarest utilizando el algoritmo A* (A search). 
Este es un problema clásico de búsqueda de caminos en grafos, donde:

- Las ciudades representan nodos
- Las carreteras entre ciudades son aristas con costos asociados (distancias)
- Necesitamos encontrar el camino con el menor costo total desde el origen (Arad) al destino (Bucarest)

El algoritmo A* es ideal para este tipo de problemas porque combina:
1. El costo real desde el nodo inicial (g(n))
2. Una estimación heurística del costo hasta el nodo objetivo (h(n))

## Aplicación del algoritmo A*

Para implementar A* en este problema:

1. **Definición de la heurística**: Usamos la distancia en línea recta (distancia euclidiana) desde cada ciudad a Bucarest como función heurística (h(n)). Esta es admisible (no sobreestima el costo real) y consistente.

2. **Función de evaluación**: f(n) = g(n) + h(n), donde:
   - g(n) = costo acumulado desde Arad hasta el nodo actual
   - h(n) = distancia heurística desde el nodo actual a Bucarest

3. **Implementación**:
   - Se expanden primero los nodos con menor f(n)
   - Se mantiene una cola de prioridad (frontera) ordenada por f(n)
   - Se registran los nodos visitados para evitar ciclos

4. **Expansión de nodos**: Para cada ciudad, consideramos todas las ciudades vecinas conectadas por carreteras.

## Optimalidad de la ruta encontrada

La ruta encontrada por A* es óptima porque:

1. **Heurística admisible**: La distancia en línea recta nunca sobrestima el costo real del camino, cumpliendo con el requisito fundamental para la optimalidad de A*.

2. **Heurística consistente**: La diferencia entre las heurísticas de nodos consecutivos no supera el costo real del paso entre ellos, lo que garantiza que el primer camino encontrado sea el óptimo.

3. **Propiedad de optimalidad de A***: Cuando se usa una heurística admisible y consistente, A* siempre encontrará la solución óptima (el camino con menor costo total).

4. **Exploración ordenada**: A* expande los nodos en orden de su costo estimado total (f(n)), asegurando que cuando se alcanza el objetivo, no existe un camino alternativo con menor costo total.

La implementación proporcionada encuentra la ruta: Arad → Sibiu → Rimnicu Vilcea → Pitesti → Bucarest, que efectivamente es la ruta óptima según las distancias proporcionadas en el problema clásico de Rumania.