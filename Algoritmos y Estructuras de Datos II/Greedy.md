Ejemplo con un problema de carga:
```
FUNCION (P,m,M): vectorDePesos(real>0) * ent>0 * ent>0 -> 

	pesoCargado <- 0
	i <- 0
		MIENTRAS i<m AND pesoCargado+P[i+1] <= M
			i <- i+1
			pesoCargado <- pesoCargado+P[i]
		FIN MIENTRAS
	retorno(i)
```
