# Clases en C++

TAD implementado como una clase:
	Una clase es un tipo definido por el usuario. Es decir, un marco que permite crear objetos que tienen su misma estructura de datos o atributos y comportamientos u operaciones comunes
![[Pasted image 20241002131407.png]]
	El nombre de la clase se puede usar para declarar objetos de la misma (duración estática, local o dinámica).


### Especificadores
*De Acceso a Miembros*: terminan con ":" y pueden aparecer varias veces en una definición de clase. La interfaz de una clase se puede dividir en:
- public
- protected: visibles a la propia clase y a sus subclases
- private: (visibles únicamente en la propia clase
*Modificadores de acceso*:
- const: indica que sus valor no admite modificaciones
- volatile: indica que su valor puede ser modificado fuera del control del compilador
*De Almacenamiento de Miembros*:
- static: Especifica que es un miembro de clase y no de objeto
*De Almacenamiento de clase*:
- extern: indica que la clase tiene visibilidad de todos los archivos que componen el programa y que el enlazado de todos los identificadores de la clase es externo.
- static: La visibilidad queda restringida a ese archivo, con enlazado interno

### Declaración de una clase
1. **class**
	- Miembros **private** por defecto pero se pueden definir como public o protected
	- Puede tener varios constructores de objetos
	- Puede participar en jerarquías de clases (herencia).
2. **struct**
	- Miembros public por defecto, pero admiten private o protected
	- Semejantes al tipo class
3. **union**
	- Miembros public. No admite otro especificador de acceso
	- Admiten un constructor
	- No pueden contener como miembro objetos que tengan constructor o destructor
	- No pueden participar de jerarquías de clases

---
**CLASS** 
*Definición de la clase*
- Se escribe entre "{ }".
- Contiene la lista completa de miembros de la clase (atributos y métodos).
- Termina con " ; ".
*Características*
- Los miembros datos de la case se describen en una lista que puede incluir datos de cualquier tipo.
- No puede ser un miembro dato de la misma clase, aunque si un puntero o referencia a ella.
- La declaración de la clase contiene los prototipos de la funciones miembros.
![[Pasted image 20241002133136.png]]
- Para definir cada función, fuera del alcance de la clase, se debe usar el operador de resolución de alcance **::** 
![[Pasted image 20241002133157.png]]
- Un identificador no puede ser simultáneamente un miembro dato y una función miembro.

Funciones Miembros Especiales:
- *Constructor*: tiene el mismo nombre de la clase
- *Destructor*: tiene el mismo nombre de la clase precedida por el carácter *" ~ "* (tilde)

- El nombre de la clase se convierte en un especificador de tipo
- Cuando se crea un objeto de una clase se llama constructor de la clase que inicializa a cada miembro dato.
- La implementación de una clase está oculta a sus clientes
- C++ permite declaraciones de clases incompletas o forward y efectuar referencias al nombre de esa clase (con punteros a la misma) antes de la clase haya sido definida totalmente.

```
class x; //definición incompleta, Exige una delcaración posterior

void f(X*a);

class Y{
	X*pX; //objeto puntero de la clase X
	...
}

class X{ //definición completa
	...
}
```

![[Pasted image 20241002154858.png]]
![[Pasted image 20241002154917.png]]
