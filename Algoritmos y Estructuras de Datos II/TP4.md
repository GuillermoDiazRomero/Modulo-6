### Punto 3
Divide&Conquer
```
función encontrarMaximo(vector, inicio, fin):
    si inicio == fin:
        retornar vector[inicio]
    
    mitad = (inicio + fin) / 2
    
    maxIzq = encontrarMaximo(vector, inicio, mitad)
    maxDer = encontrarMaximo(vector, mitad + 1, fin)
    
    retornar máximo(maxIzq, maxDer)


```

### Punto 4
Divide&Conquer
```
función esVocal(caracter):
    retornar caracter en ('a', 'e', 'i', 'o', 'u')

función tieneVocalesIguales(palabra, inicio, fin):
    si fin - inicio < 1:
        retornar falso
    
    mitad = (inicio + fin) / 2
    
    si tieneVocalesIguales(palabra, inicio, mitad) o tieneVocalesIguales(palabra, mitad + 1, fin):
        retornar verdadero
    
    si esVocal(palabra[mitad]) y esVocal(palabra[mitad + 1]) y palabra[mitad] == palabra[mitad + 1]:
        retornar verdadero
    
    retornar falso

```

### Punto 5
Divide&Conquer
```
función contarParesImpares(vector, inicio, fin):
    si inicio == fin:
        si vector[inicio] es par:
            retornar 1
        más:
            retornar -1
    
    mitad = (inicio + fin) / 2
    
    paresImparesIzq = contarParesImpares(vector, inicio, mitad)
    paresImparesDer = contarParesImpares(vector, mitad + 1, fin)
    
    retornar paresImparesIzq + paresImparesDer

```


### Punto 6
Decrease&Conquer
```
función cortarChocolate(filas, columnas):
    retornar (filas * columnas) - 1
```