# Backtracking

2. Dado un número entero M y un vector V de n números naturales, se quiere determinar si existe una forma de insertar entre los n números del vector (en el mismo orden en que están colocados en el vector) operadores de suma y resta de forma tal que se obtenga una expresión aritmética con el valor de M como resultado final. Se quiere comprobar si es posible llegar a una solución, y en ese caso mostrar la o las expresiones de suma M.
![[Pasted image 20241029104510.png]]
```
FUNCION AgregarOperadores(V,A,i,j): Vector x Vector --> bool

// Globales: M (resultado), n (longitud del vector V)
// Entrada: V (Vector con n elementos enteros), A (Vector auxiliar vacio), n(posicion del vector V, viene iniciada en 0), l (posicion del vector A, viene iniciada en 0)
// Salida: A (vector con los operadores agragados)

	SI (n = 0)
		return false
	SINO
		SI (n = 1) ENTONCES
			SI (V[n] = M) ENTONCES
				ESCRIBIR V
				RETORNO true
			SINO
				ESCRIBIR (No tiene solucion)
				RETORNO false
			FIN SI
		SINO
			SI




		SI (V = 1 and j=0) ENTONCES
			A[0] = V[0]
			BORRAR V[0]
			A[1] = +
			AgregarOperadores (V,A,)
			A[1] = -
			AgregarOperadores (V,A)
		SINO
			A[l] = V[0]
			A[l+1] = +
			BORRAR V[0]
			AgregarOperadores (V,A)
			A[l] = -
			AgregarOperadores (V,A)
		FIN SI
	FIN SI
FIN FUNCION
```