# Backtracking

2. Dado un número entero M y un vector V de n números naturales, se quiere determinar si existe una forma de insertar entre los n números del vector (en el mismo orden en que están colocados en el vector) operadores de suma y resta de forma tal que se obtenga una expresión aritmética con el valor de M como resultado final. Se quiere comprobar si es posible llegar a una solución, y en ese caso mostrar la o las expresiones de suma M.
![[Pasted image 20241029104510.png]]
```
FUNCION AgregarOperadores(V,A,i,j): Vector x Vector x Ent >= 0 x Ent >= 0 --> bool

// Globales: M (resultado), n (longitud del vector V)
// Entrada: V (Vector con n elementos enteros), A (Vector auxiliar vacio), i(posicion del vector V, viene iniciada en 0), j (posicion del vector A, viene iniciada en 0)
// Salida: A, retorno true si hay soluciones o false si no hay

	SI (n = 0)
		return false
	SINO
		SI (i = n) ENTONCES
			A[j] <-- V[n]
			SI (suma(A) = M) ENTONCES
				ESCRIBIR (V)
				RETORNO true
			SINO
				ESCRIBIR ("No tiene solucion")
				RETORNO false
			FIN SI
		SINO
			A[j] <-- V[i]
			A[j+1] <-- +
			resul1 <-- AgregarOperadores(V,A,i+1,j+2)
			A[j+1] <-- -
			resul2 <-- AgregarOperadores(V,A,i+1,j+2)
			RETORNO (resul1 OR resul2)
	FIN SI
FIN FUNCION
```

Otra opción:
```
FUNCION AgregarOperadores(V, A, i, j): Vector x Vector x Ent >= 0 x Ent >= 0 --> bool
// Globales: M (resultado), n (longitud del vector V)
// Entrada: V (Vector con n elementos enteros), A (Vector auxiliar vacío), i (posición en V), j (posición en A)
// Salida: A, retorno true si hay soluciones o false si no hay
	SI (i = n) ENTONCES
		SI (evaluarExpresion(A) = M) ENTONCES
			ESCRIBIR (A)
			RETORNO true
		SINO
			RETORNO false
		FIN SI
	FIN SI
	A[j] <-- V[i]
	A[j+1] <-- "+"
	SI (AgregarOperadores(V, A, i+1, j+2)) ENTONCES
		RETORNO true
	FIN SI
	A[j+1] <-- "-"
	SI (AgregarOperadores(V, A, i+1, j+2)) ENTONCES
		RETORNO true
	FIN SI
	RETORNO false
FIN FUNCION

FUNCION evaluarExpresion(A): Vector --> Ent
	resultado <-- A[0]
	indice <-- 1
	MIENTRAS (indice < longitud(A))
		SI (A[indice] = "+") ENTONCES
			resultado <-- resultado + A[indice + 1]
		SINO SI (A[indice] = "-") ENTONCES
			resultado <-- resultado - A[indice + 1]
		FIN SI
		indice <-- indice + 2
	FIN MIENTRAS
	RETORNO resultado
FIN FUNCION
```