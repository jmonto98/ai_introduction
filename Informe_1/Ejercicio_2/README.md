## Respuestas a las preguntas del taller:

### 1. Estructura del problema y funciones:

- **Actions:**  
  Las acciones posibles son moverse arriba, abajo, izquierda o derecha (definidas en el diccionario `actions` de la clase `Problem`).

- **Result:**  
  La función `result` calcula el nuevo estado aplicando una acción a un estado actual.

- **Action-cost:**  
  Todos los movimientos tienen costo 1 (función `action_cost`).

### 2. Cambio en la función de costo:

- Si cambiamos la función de costo (por ejemplo, dar más costo a movimientos verticales), el algoritmo priorizará caminos con más movimientos horizontales. Esto afectaría la optimalidad del camino encontrado.

### 3. Múltiples salidas:

- Implementé una función `find_nearest_exit` que busca todas las salidas y encuentra el camino más corto a cualquiera de ellas.
  
- El algoritmo se modifica para evaluar cada salida potencial y seleccionar la más cercana.

### 4. Limitaciones del algoritmo:

- **Complejidad:**  
  A* puede ser costoso en memoria para laberintos muy grandes.

- **Heurística:**  
  La distancia de Manhattan no siempre es la mejor heurística, especialmente en laberintos con muchos obstáculos.

- **Óptimo local:**  
  Puede quedar atrapado en caminos que parecen prometedores pero llevan a callejones sin salida.

- **Una sola meta:**  
  La implementación básica solo busca una meta a la vez.

### 5. Mejoras implementadas:

- Rastreo de acciones tomadas (no solo posiciones).
- Manejo de múltiples salidas.
- Validación de posiciones en el laberinto.
- Laberinto más grande con diferentes obstáculos.