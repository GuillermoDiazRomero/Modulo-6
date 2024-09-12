## Paradigma Lógico:
Asume un conjunto de hecho y un conjunto de reglas que permiten deducir nuevos hechos.

Se implementó en base a las cláusulas de Horn, que son un subconjunto de la lógica de predicados.

***Cláusulas de Horn:*** Forma restrictiva de lógica de predicados que para cada cláusula hay una sola conclusión.

La fórmula lógica es una Cláusula de Horn si es una cláusula con un literal positivo como máximo
	Ejemplo:
			***¬p v ¬q v ... v ¬t v u***
			(p ^ q ^ ... ^ t) --> u
La notación casual de la lógica de predicados combina variables, constantes y expresiones:
![[Pasted image 20240828113245.png]]
	**Hechos:** fórmulas atómicas (las proposiciones p,q,t,u)
	**Reglas:** fórmulas de la forma ( p ^ q ^ ... ^ t )--> u

**Programación Lógica:** es una instrucción de componentes lógicos de un algoritmo
**Programa:** Conjunto de declaraciones formales de especificaciones que deben ser correctas por definición.

En este tipo de programación, la evaluación empieza definiendo una **meta** e intentando probar que ella de deduce de alguna regla

**meta:** se deduce de una regla si todos los antecedentes de la regla se verifican con la transformación existente. Los antecedentes se convierten en nuevas metas que deben resolverse vía otras reglas. El proceso termina cuando todas las submetas han sido probadas

Problema:
- Definir el mecanismo de búsqueda adecuado para las reglas
- Búsqueda DFS (Deep First Search) con un proceso de Backtracking

### Paradigmas Lógico
 ***Pseudo declarativo***
 - Ordena cuidadosamente los hechos como las reglas
 - Usa **mecanismos de corte (!)**, que son dispositivos no lógicos que impiden el mecanismo de backtracking y fueron introducidos para aumentar la eficiencia de los mecanismos de búsqueda.

**Un programa lógico** se configura como un conjunto de hechos y reglas lógicas previamente establecidas, que obtienen conclusiones en base a una serie de preguntas.

Un programa con este paradigma se define tal que:
![[Pasted image 20240828135723.png]]
![[Pasted image 20240828135756.png]]

## Lenguaje PROLOG
- Predicados (hecho): expresan propiedades de los objetos
![[Pasted image 20240828141722.png]]
- Cláusulas: definen reglas lógicas que permiten cambiar otros conceptos al aplicarlas a una Base de Conocimiento.
![[Pasted image 20240828141907.png]]
![[Pasted image 20240828141917.png]]
![[Pasted image 20240828141930.png]]
