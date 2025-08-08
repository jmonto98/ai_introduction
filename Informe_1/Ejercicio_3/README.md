## Respuestas a las preguntas del taller:

## Diferencias entre BFS e IDS

### BFS (Breadth-First Search)

- **Ventaja**: Encuentra siempre el camino más corto (óptimo).
- **Desventaja**: Usa más memoria (almacena todos los nodos en el nivel actual).
- **Tiempo**: Generalmente más rápido para soluciones cercanas al inicio.

### IDS (Iterative Deepening Search)

- **Ventaja**: Más eficiente en memoria (solo almacena la rama actual).
- **Desventaja**: Puede ser más lento al repetir búsquedas en profundidades menores.
- **Tiempo**: Más lento en algunos casos, pero mejor en memoria para grafos grandes.

---

En este caso, **ambos algoritmos encuentran el mismo camino óptimo** (`A → C → F → J`), pero **BFS es ligeramente más rápido**, mientras que **IDS usa menos memoria**.
