# Paradigma funcional

---
- [I] [[L8.V1.Paradigma Funcional.pdf]]
---

- [i] Se basa en la composición de funciones, es decir, el resultado de una función ingresa en otra y así sucesivamente hasta obtener el resultado deseado. Programar en este paradigma implica:
- Programar sin variables mutables ni asignaciones (no existe el concepto de celdas de memoria)
- Evitar sentencias imperativas de control
- Sin efecto secundario o lateral
- Las funciones tienen *transparencia referencial*. El valor de una función no depende del historial del programa ni el orden de instrucciones, una misma función con una misma entrada siempre devuelve el mismo valor.
- Concepto de función como objeto de 1era clase, es decir:
	- son tratadas como datos, pueden pasarse por parámetro, ser devueltas como valores, entre otros.
	 * pueden definirse en cualquier lugar, incluso dentro de otras funciones.

## Puntos de vista desde el paradigma funcional

Este paradigma puede ser visto desde el punto de vista **procedimental** o **declarativo**. Si lo trabajamos como procedimental, una función se especifica indicando la secuencia de ejecución. Desde el punto de vista declarativo una función se especifica matemáticamente mediante su definición sin establecer la secuencia de control específicamente.

Ejemplo de una función que calcula el MCD con el paradigma funcional desde el punto de vista declarativo:
![[Pasted image 20240903115543.png]]
Observemos que una función se define como una colección de transformaciones (o comportamientos) y a partir de ella definen una función computacionalmente. Este modelo usa una *evaluación diferida (no estricta)*, en este tipo de evaluación los argumentos. de una función son evaluados cuando son requeridos (en C por ej. es al revés).

## Programa funcional

- [i] Un *programa funcional* es un conjunto. compuestos de funciones que juntas definen un objetivo específico de la aplicación. Un programa funcional se define por la siguiente ecuación:![[Pasted image 20240903120107.png]]
# Lenguaje HASKELL

---
- [ ] [[L8.V2.HASKELL -  Paradigma Funcional.pdf]]
---

Recordemos que los lenguajes funcionales implementan:![[Pasted image 20240903121251.png]]
## Cositas de haskell

+ **Objetos de datos**: átomos, identificadores y listas se definen igual que en PROLOG:![[Pasted image 20240903121441.png]]
+ **Funciones primitivas del lenguaje**: hay para distintos propósitos
	+ Para tratamiento de listas: ![[Pasted image 20240903121616.png]] ![[Pasted image 20240903121605.png]] ![[Pasted image 20240903121703.png]]
	+ Para la asignación, relaciones bool y predicados: ![[Pasted image 20240903121902.png]]
	+ Aritméticas:![[Pasted image 20240903121932.png]]
	+ Condicionales:![[Pasted image 20240903122144.png]]
+ **Formas funcionales** para crear y combinar funciones![[Pasted image 20240903122234.png]]
### Generación de listas

- [i] En haskell podemos generar un rango de números en una lista de la siguiente manera: **[0..10]**, esto generará una lista de números del 0 al 10. Además, cuando ponemos un número inicial, el paso será determinado según la diferencia entre la cabecera y el primer número, de tal manera que **[10|8..0]** generará una lista que comenzará por 10, y será seguida de una lista de números del 8 al 0 con paso 2.

## Formas de definir funciones en HASKELL

1.  **PATTERN MATCHING**: especifica los patrones a los que deben adaptarse los datos para luego deconstruirlos y obtener un resultado. Por ej., para fibonacci:![[Pasted image 20240906130135.png]]
- [!] Los patrones se verifican de arriba hacia abajo y cuando un dato coincide con un pattern, lo usa. Si un dato no cae en ninguno de los patrones definidos para x función, HASKELL lanzará el error *Non-exhaustive patterns in function XXXX* 

2. **GUARDS**: son una forma de comprobar si alguna propiedad de un valor (o varias de ellas) es V o F. Por ejemplo, para calcular el fibonacci:![[Pasted image 20240903134129.png]]
- [!] Las sentencias posteriores a *|* son casos de *n*, *otherwise* significa "cualquier otro caso".

3. **LIST COMPREHENSION**: permite construir a partir de conjuntos generales un conjunto más específico. Por ejemplo, obtener los diez primeros números pares: $C\,=\,\{2x / x \in [1,10]\}$:![[Pasted image 20240906130705.png]]
## High Order Programming

- [i] En haskell se pueden tomar funciones como parámetros y devolver funciones como valores de retorno. Una función que hace alguna de estas cosas se llama *Función de Orden Superior*.![[Pasted image 20240906131215.png]]

