### Pilares de la POO

- Abstracción: es encarada desde el punto de vista de POO expresa las características esenciales del objeto.
- Encapsulamiento: Visto en el proyecto de Dragon Ball Sparking Lucky, al momento de elegir la privacidad de un método (private o public).
- Herencia: Relación entre do clases, concepto de clase padre y clase hijo.
- Polimorfismo: Capacidad dinámica del comportamiento de una clase según su herencia.

#Abstracción:
omitimos detalles irrelevantes para representar lo necesario.

```
 class Empleado{
	 //encapsulamientos
	 //métodos
 }
Empleado EmpleadoA = new Empleado();
var empleadoB = new Empleado();
```
Con esto podemos crear varios tipos de empleados

- Atributos: son características individuales que diferencian un objeto de otro
- Método: se define adentro de una clase y representan el comportamiento de un objeto
- Propiedades: Identificador con un determinado tipo de dato


Miembros de una clase:
	Se representan como un circulo con puntos adentro (siendo los datos los puntos y la clase el circulo)
	![[Pasted image 20240821173249.png]]
Los datos son los atributos y las acciones son los métodos

Principio de ocultamiento de información:
![[Pasted image 20240821173331.png]]

Encapsulamiento:
- private
- public



Clase Métodos:
	La firma de un método esta constituida por un nombre y parámetros (puede no tener)
Llamamos método a una función que nos permite acceder a las variables declaradas dentro de una #class
![[Pasted image 20240821173949.png]]

**La sobrecarga de un método** es cuando tengo varios métodos con el mismo nombre pero con distintos tipos de parámetros, durante la ejecución, el código tiene la capacidad de decidir según el tipo de parámetro hacia cual método se debe dirigir.
	Esto puede servir para tener un mayor control sobre las cosas que manda el usuario a nuestro programa
**Método Constructor**: Es un método que tiene el mismo nombre al de su tipo. También se puede hacer una sobrecarga del constructor y un constructor vacío.


## Arquitectura de una aplicación POO

Una aplicación constituida usando **Paradigma** orientado a objetos esta constituido por múltiples clases que interactuan entre sí
![[Pasted image 20240821182055.png]]

Asociación entre clases:
- Composición: La composición es un relación más fuerte que la agregación
![[Pasted image 20240821182531.png]]
	Ejemplo: Salón es **parte de** un colegio
- Agregación: es la relación más débil de las clases
![[Pasted image 20240821182651.png]]
Ejemplo: El curso **tiene un** estudiante.

Ejemplo de las dos unidas:
![[Pasted image 20240821182839.png]]
![[Pasted image 20240821182848.png]]

