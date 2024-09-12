### Punto 1 b
```
Luego de preguntar puedo pedir tipos de pregunta
	";" para la siguiente solución
	"a" para todas las soluciones
	"RET" para detener 
```

?- progenitor(carlos, X). 
	X = isabelII ?
	yes
?- progenitor(X, carlos). 
	X = william ?
	yes
?- progenitor(X, carlos), progenitor(charlotte, X).
	X =  william ?
	yes
?- progenitor(William, X), progenitor(harry, X).
	X = carlos
	yes

### Punto 1c
?- progenitor (harry,X).
?- progenitor (X,william).
?- progenitor(louis,Y), progenitor(Y,X).
