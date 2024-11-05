# Backtracking

## Punto 2

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

Otra opción (no recomiendo):
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

Implementación
```
#include <iostream>
#include <vector>
#include <string>

using namespace std;

// Variables globales
int M; // Resultado deseado
int n; // Longitud del vector V

// Función para evaluar la expresión generada en el vector A
int evaluarExpresion(const vector<string>& A) {
    int resultado = stoi(A[0]);
    for (size_t i = 1; i < A.size(); i += 2) {
        string operador = A[i];
        int valor = stoi(A[i + 1]);
        
        if (operador == "+") {
            resultado += valor;
        } else if (operador == "-") {
            resultado -= valor;
        }
    }
    return resultado;
}

// Función de Vuelta Atrás para intentar encontrar una combinación de operadores que sume M
bool agregarOperadores(const vector<int>& V, vector<string>& A, int i) {
    // Si hemos alcanzado el final del vector V, evaluamos la expresión
    if (i == n) {
        if (evaluarExpresion(A) == M) {
            // Imprimir la solución encontrada
            for (const string& elem : A) {
                cout << elem << " ";
            }
            cout << "= " << M << endl;
            return true;
        }
        return false;
    }

    // Agregar el número actual de V a A
    A.push_back(to_string(V[i]));
    
    // Intentar con el operador +
    A.push_back("+");
    if (agregarOperadores(V, A, i + 1)) return true;
    A.pop_back(); // Deshacer el operador +

    // Intentar con el operador -
    A.push_back("-");
    if (agregarOperadores(V, A, i + 1)) return true;
    A.pop_back(); // Deshacer el operador -

    // Deshacer el número actual
    A.pop_back();

    return false;
}

int main() {
    // Datos de entrada del ejemplo 1
    M = 12;
    n = 5;
    vector<int> V = {1, 4, 3, 1, 5};

    // Vector auxiliar para construir la expresión
    vector<string> A;

    cout << "Intentando encontrar una combinacion de operadores para sumar " << M << "..." << endl;
    if (!agregarOperadores(V, A, 0)) {
        cout << "No tiene solucion" << endl;
    }

    return 0;
}

```



## Punto 3

3. Se disponen números enteros positivos en un triángulo equilátero de base n como se muestra en el ejemplo de la figura. Se desea encontrar la suma mínima descendiendo desde el vértice superior del triángulo hasta su base a través de una secuencia de números adyacentes (indicados en la figura mediante círculos).
![[Pasted image 20241105001120.png]]
```
FUNCION sumaMinima(fila, columna): Ent >= 0 x Ent >= 0 ---> Matriz[n][n]
// Globales: n (número de filas en el triángulo), memo (matriz n x n, llena con -1)
// Entradas: fila (viene inicializado en 0), columna (viene inicializado en 0)
// Salidas:
	SI (fila == n - 1) ENTONCES 
		RETORNO triangulo[fila][columna] 
	FIN SI
	SI (memo[fila][columna] != -1) ENTONCES 
		RETORNO memo[fila][columna] 
	FIN SI 
	sumaIz <- sumaMinima(fila + 1, columna) 
	sumaDer <- sumaMinima(fila + 1, columna + 1) 
	memo[fila][columna] <- triangulo[fila][columna] + mínimo(sumaIz, sumaDer) 
	RETORNO memo[fila][columna] 
FIN FUNCION
```

Implementación:
```
#include <iostream>
#include <vector>
#include <algorithm>

using namespace std;

// Tamaño del triángulo
const int n = 5; // Cambia este valor según el tamaño de tu triángulo
int triangulo[n][n] = {
    {2, 0, 0, 0, 0},
    {3, 4, 0, 0, 0},
    {6, 5, 7, 0, 0},
    {4, 1, 8, 3, 0},
    {9, 2, 0, 0, 0}
};

// Matriz para memoización
int memo[n][n];

// Función que calcula la suma mínima
int sumaMinima(int fila, int columna) {
    // Caso base: si estamos en la última fila
    if (fila == n - 1) {
        return triangulo[fila][columna];
    }
    
    // Verificar si el valor ya ha sido calculado
    if (memo[fila][columna] != -1) {
        return memo[fila][columna];
    }
    
    // Calcular las sumas de las siguientes filas
    int sumaIz = sumaMinima(fila + 1, columna);
    int sumaDer = sumaMinima(fila + 1, columna + 1);
    
    // Almacenar el resultado en memo y retornar
    memo[fila][columna] = triangulo[fila][columna] + min(sumaIz, sumaDer);
    return memo[fila][columna];
}

// Función principal
int main() {
    // Inicializar la matriz memo con -1
    for (int i = 0; i < n; ++i) {
        for (int j = 0; j < n; ++j) {
            memo[i][j] = -1;
        }
    }

    // Llamar a la función desde la parte superior del triángulo
    int resultado = sumaMinima(0, 0);
    
    // Imprimir el resultado
    cout << "La suma mínima es: " << resultado << endl;

    return 0;
}

```

a