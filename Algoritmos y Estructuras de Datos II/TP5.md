
### Pseudocódigo del algoritmo Greedy para la selección de actividades




```
Entrada: N (número de actividades) y una lista de actividades con sus horas de inicio (Hi) y horas de finalización (Hf). 
Salida: Número máximo de actividades que se pueden realizar sin solaparse.  
1. Ordenar las actividades en orden ascendente por su hora de finalización (Hf).  
2. Inicializar `contador` a 1 (asumiendo que la primera actividad ya está seleccionada).    Establecer `ultimaHoraFinalizacion` como la hora de finalización de la primera actividad.  
3. Para cada actividad `i` desde la segunda actividad hasta la N-ésima:    
	a. Si la hora de inicio de la actividad `i` (Hi) es mayor o igual a `ultimaHoraFinalizacion`:       
		- Incrementar `contador` en 1.       
		- Actualizar `ultimaHoraFinalizacion` a la hora de finalización de la actividad `i` (Hf).  
4. Retornar `contador` como el número máximo de actividades que se pueden realizar.``
```

### Ejemplo paso a paso:

Supongamos que tenemos las siguientes actividades con sus horas de inicio y finalización:

| Actividad | Hora de inicio (Hi) | Hora de finalización (Hf) |
| --------- | ------------------- | ------------------------- |
| A1        | 1                   | 3                         |
| A2        | 2                   | 5                         |
| A3        | 4                   | 6                         |
| A4        | 6                   | 8                         |
| A5        | 5                   | 7                         |

1. **Ordenar por hora de finalización**:
    
    - A1 (Hi: 1, Hf: 3)
    - A2 (Hi: 2, Hf: 5)
    - A3 (Hi: 4, Hf: 6)
    - A5 (Hi: 5, Hf: 7)
    - A4 (Hi: 6, Hf: 8)
2. **Seleccionar la primera actividad**:
    
    - Seleccionamos A1, ya que es la que termina más temprano. `ultimaHoraFinalizacion` = 3.
    - `contador` = 1.
3. **Verificar las siguientes actividades**:
    
    - A2: Hi (2) < `ultimaHoraFinalizacion` (3), no se puede seleccionar.
    - A3: Hi (4) >= `ultimaHoraFinalizacion` (3), se puede seleccionar. Actualizamos `ultimaHoraFinalizacion` = 6 y `contador` = 2.
    - A5: Hi (5) < `ultimaHoraFinalizacion` (6), no se puede seleccionar.
    - A4: Hi (6) >= `ultimaHoraFinalizacion` (6), se puede seleccionar. Actualizamos `ultimaHoraFinalizacion` = 8 y `contador` = 3.
4. **Retornar el resultado**:
    
    - El número máximo de actividades que se pueden realizar es `3`.

Este pseudocódigo y ejemplo muestran cómo implementar el enfoque Greedy para seleccionar el número máximo de actividades sin solapamiento. Si necesitas la implementación en un lenguaje de programación específico, como C#, Python o cualquier otro, avísame y te lo desarrollo.





---
### a. Diseño del algoritmo Greedy para determinar en qué estaciones parar

La idea es detenerse en la estación de servicio más lejana posible, siempre que esté dentro del rango de autonomía del tanque de gasolina.

### Pseudocódigo:

plaintext

Copiar código

```
Entrada:  - `distanciaTotal`: la distancia total entre las dos ciudades. - `n`: la autonomía del bus (máxima distancia que puede recorrer con un tanque lleno). - `estaciones`: una lista con las distancias de cada estación desde el punto de partida, ordenadas en orden ascendente.  Salida:  - `paradas`: lista con las estaciones en las que se debe parar. - `numParadas`: número mínimo de paradas necesarias.  1. Inicializar `paradas` como una lista vacía. 2. Inicializar `posicionActual` a 0 (la posición de inicio). 3. Inicializar `numParadas` a 0.  4. Mientras `posicionActual + n < distanciaTotal`:    a. Encontrar la estación más lejana a la que se puede llegar desde `posicionActual` y que esté dentro del rango (`posicionActual + n`).    b. Si no hay una estación que cumpla la condición, retornar "Imposible llegar a destino".    c. Si hay una estación que cumple:       - Actualizar `posicionActual` a la posición de esa estación.       - Añadir la posición de la estación a la lista `paradas`.       - Incrementar `numParadas` en 1.  5. Retornar `paradas` y `numParadas`.
```

### b. Justificación de que la estrategia encuentra siempre una solución óptima

La estrategia Greedy selecciona la estación más lejana posible dentro del rango de autonomía del bus. Esto garantiza que se cubre la mayor distancia posible con cada tanque lleno, lo que minimiza el número de paradas.

La razón por la que este enfoque Greedy es óptimo es que, en cada paso, intenta maximizar la distancia recorrida antes de repostar. Al elegir siempre la estación más lejana alcanzable, se evita detenerse innecesariamente en estaciones intermedias, lo que llevaría a realizar más paradas de las necesarias.

### c. Estimación del costo del algoritmo

- **Ordenar las estaciones (si no están ordenadas):** O(Mlog⁡M)O(M \log M)O(MlogM), donde MMM es el número de estaciones.
- **Buscar la estación más lejana alcanzable:** Esto se puede hacer con una búsqueda lineal por cada parada, lo cual es O(M)O(M)O(M).
- **Ciclo de búsqueda de paradas:** En el peor caso, se revisan todas las estaciones para encontrar la siguiente parada, por lo que el tiempo de ejecución es O(M)O(M)O(M).

Por lo tanto, la complejidad total del algoritmo es O(Mlog⁡M)O(M \log M)O(MlogM) si se incluye el costo de ordenar, o O(M)O(M)O(M) si las estaciones ya vienen ordenadas.

Este algoritmo Greedy resuelve el problema de manera eficiente y garantiza encontrar la solución óptima de paradas para minimizar el número de recargas de combustible. ¡Espero que te sea útil! Si necesitas más detalles o una implementación en código, avísame.