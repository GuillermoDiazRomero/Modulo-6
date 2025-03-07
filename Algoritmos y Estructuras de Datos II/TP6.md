### Punto 2: Problema de la Mochila Múltiple

#### Enunciado

1. **Definir el arreglo de Programación Dinámica**: Sea dp[j]dp[j]dp[j] el máximo beneficio que se puede obtener con una mochila de capacidad jjj.
2. **Ecuación de Recurrencia**:
    dp[j]=max⁡(dp[j],dp[j−pi]+bi) para cada i,cuando j≥pi
    Esta ecuación indica que para cada peso "i", se decide si incluir el objeto iii en la mochila, maximizando el beneficio.
3. **Implementación del Algoritmo**: Aquí se muestra el pseudocódigo del algoritmo:

```
FUNCION mochila_multiple(pesos, beneficios, capacidad)
    Crear arreglo DP con tamaño (capacidad + 1), inicializado en 0

    PARA (j = 1 , ... , capacidad) HACER
        PARA (i = 0, ... , (longitud(pesos) - 1) ) HACER
            SI j >= pesos[i] ENTONCES
                DP[j] = máximo( DP[j], DP[j - pesos[i]] + beneficios[i] )
            FIN SI
        FIN PARA
    FIN PARA

    RETORNO DP[capacidad]
FIN FUNCION
```

// Parámetros de entrada
pesos = [3, 1, 2, 4, 1]
beneficios = [66, 20, 30, 90, 10]
capacidad = 10

// Llamada a la función y salida
beneficio_maximo = mochila_multiple(pesos, beneficios, capacidad)
Imprimir "El beneficio máximo que se puede obtener es:", beneficio_maximo


```
FUNCION mochilaMultiple (i, peso, mochila[]) :   -->
	//Globales
	//n: cantidad de objetos
	//M: peso máximo de la mochila
	//b[]: vector con los beneficios de los objetos
	//p[]: vector con los pesos de los objetos

	//i viene inicializada en 0
	//peso viene inicializado en 0

	PARA (i = 1 , ... , n) HACER
		PARA (j = 0, ... , M) HACER
			SI (j = 0) ENTONCES
				V(i,j) <-- 0
			FIN SI
			SI (i = 1) ENTONCES
				V(i,j) <-- 
			
			
```





---

### Punto 3: Suma Mínima en un Triángulo


1. **Definir la Estructura de Datos**: Usa una matriz para representar el triángulo, donde cada elemento tri[i][j]tri[i][j]tri[i][j] representa el valor en la fila iii y columna jjj del triángulo.
    
2. **Ecuación de Recurrencia**: Para calcular la suma mínima en el camino desde la cima hacia la base, se utiliza la siguiente recurrencia:
    
    dp[i][j]=tri[i][j]+min⁡(dp[i+1][j],dp[i+1][j+1])dp[i][j] = \text{tri}[i][j] + \min(dp[i+1][j], dp[i+1][j+1])dp[i][j]=tri[i][j]+min(dp[i+1][j],dp[i+1][j+1])
    
    Comienza desde la base del triángulo y avanza hacia arriba, acumulando la suma mínima en cada posición.
    
3. **Implementación del Algoritmo**:
    

```
Función suma_minima_triangulo(triangulo)
    // Inicializar DP con la última fila del triángulo
    DP = copia(triangulo[última_fila])

    // Recorrer el triángulo de abajo hacia arriba
    Para i desde longitud(triangulo) - 2 hasta 0 hacer
        Para j desde 0 hasta longitud(triangulo[i]) - 1 hacer
            DP[j] = triangulo[i][j] + mínimo(DP[j], DP[j + 1])
        Fin Para
    Fin Para

    // La primera posición contendrá la suma mínima
    Retornar DP[0]
Fin Función
```

// Ejemplo de triángulo
triangulo = [
    [2],
    [3, 4],
    [6, 5, 7],
    [4, 1, 8, 3]
]

// Llamada a la función y salida
suma_minima = suma_minima_triangulo(triangulo)
Imprimir "La suma mínima para descender por el triángulo es:", suma_minima

4. **Resultado**: Al ejecutar este algoritmo, el valor resultante será la suma mínima para llegar a la base del triángulo desde el vértice superior.


![[Imagen de WhatsApp 2024-10-29 a las 09.07.07_ce7f9ec5.jpg]]