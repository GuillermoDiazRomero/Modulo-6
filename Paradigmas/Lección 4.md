# **Programación Orientada a Objetos (POO)**

## Introducción
Es una disciplina de ingeniería de desarrollo y modelado de software que permite construir fácilmente sistemas complejos a partir de componentes individuales.

Es una metodología de análisis, diseño y programación que configura las fases fundamentales del ciclo de vida de un sistema informático.

![[Pasted image 20240912132854.png]]

Aspectos básicos de la Orientación de Objetos:
- Estructura modular basada en objetos
- Abstracción de datos
- Gestión automática de memoria
- Clases
- Herencia
- Polimorfismo y enlace dinámico
- Herencia Múltiple y Repetida

A un objeto se le solicita realizar un **servicio** mediante el envío a ese objeto del mensaje adecuado. Formando la siguiente ecuación:
![[Pasted image 20240912133601.png]]
	Objeto: es una instancia de una clase, la que implementa un tipo abstracto de dato (TAD)
	Mensaje: Información específica que se envía al objeto para que ejecute una determinada tarea.

Lenguajes que admiten Orientación a Objetos:
- SMALLTALK: potente sistema informático donde el usuario puede almacenar y manipular la información ágilmente. Ahora se usa para lenguaje académico
- C++
- Object Pascal
- Sa

### !Importante!
POO es un Paradigma Procedimental con Efecto Lateral

---
---
## Ideas Fundamentales

![[Pasted image 20240912134546.png]]

El método de implementación en el que los programas son organizados como colecciones cooperativas de objetos, cada uno de los cuales representa una instancia de alguna clase, y cuya clases son miembros de jerarquías de clases unidas a través de una relación de herencia.
![[Pasted image 20240912135356.png]]

### Clases y Tipos Abstractos de Datos
![[Pasted image 20240912135621.png]]

![[Pasted image 20240912135850.png]]

Ejemplo con el ADT Pila:
![[Pasted image 20240912140027.png]]

### Clases y Tipos de Abstractos de datos:

![[Pasted image 20240912140257.png]]

Clases: son descripciones estáticas de un conjunto de objetos que son las instancias de la clase.

Estructura de Datos (Común a todos los objetos de la clase): El objeto contiene una copia local de las variables que componen la estructura de datos y le asigna un valor particular a cada una. Esos **valores particulares** determinan el **estado del objeto**.

Métodos: Operaciones comunes a todos los objetos de la clase. Existe una única copia de la implementación del método en la clase y todos los objetos de la misma la comparten.

Por lo tanto:
	Clases  (Especifican) ---> Estructuras de Datos ^ Métodos

![[Pasted image 20240912141343.png]]


Objetos: Entidad real o abstracta, acerca de la cual almacenamos datos y los métodos que controlan dichos datos.
![[Pasted image 20240912142255.png]]

Objeto: Elemento autónomo de información, creado en tiempo de ejecución que proporciona servicios sobre la estructura de datos que implementa. Un objeto tiene
- Estado: determinado por su estructura estática y su estructura dinámica
- Comportamiento: Se determina analizando como reacciona al recibir un mensaje y cómo cambia su estado
- Identidad: cada objeto tiene una identidad inherente al objeto, que permanentemente está asociada a él.

Ejemplo de estado de un Objeto:
![[Pasted image 20240912142929.png]]