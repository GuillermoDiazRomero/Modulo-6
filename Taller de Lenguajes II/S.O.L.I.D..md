**S**ingle Responsibility Principle
**O**pen/Closed Principle
**L**iskov Substitution Principle
**I**nterface Segregation Principle
**D**ependency Inversión Principle

## **S**ingle Responsibility Principle

	Establece que una clase debe tener una única responsabilidad o una única tarea. Las clases tienen que tener una sola razón para cambiar.

Ejemplo:
```
public class Libro{
	//atributos publicos

	//Constructor
	public Libro(argumentos){
		Variable = variable
	}
	public void GuardarEnArchivo{
		//Agrego el libro al listado de contenido
	}
	public devolverLibro{
		//Código
		return libro
	}
}
```


## Pilares de la POO
**Herencia:** es un tipo de relación donde un objeto es creado a partir de otros objetos ya existentes. Se usa la expresión "X **Es un** Y"
![[Pasted image 20240828174717.png]]

**Polimorfismo:** Proviene del griego, que significa "con muchas formas" y tiene dos aspectos diferentes:
- virtual: adentro de una clase se crea un método virtual 
- override: sobrescribe en cada clase derivada para dibujar la forma determinada.

![[Pasted image 20240828180101.png]]



**Liskov Substitution Principle:** Los objetos de la clase derivada deben comportarse coherentemente con los comportamientos de las clases padres.



