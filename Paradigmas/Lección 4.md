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

**!Importante!**
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

### Identidad de un Objeto

![[Pasted image 20240913003542.png]]

- La identidad del objeto se correspondía con su nombre con su nombre siendo imposible separar ambos conceptos.
- Al incorporarse a los lenguajes de programación, la asignación dinámica de memoria desaparece esta correspondencia.
- Referencia: permite que un mismo objeto tenga varios nombres ("alias"), desvirtúa la relación nombre/identidad del objeto.
- Disociación entre el nombre del objeto y su identidad, se produce con el uso de subprogramas

![[Pasted image 20240913004950.png]]


### Métodos
Especifican la forma en que controlan los datos de un objeto y representan el comportamiento de ese tipo de objetos (son lo que conocemos como funciones)
![[Pasted image 20240913005708.png]]

**Comportamiento de un objeto**
Tipos de operaciones:
- Modificar: operación que altera el estado del objeto
- Seleccionar: operación que accede al estado del objeto, pero no lo altera
- Iterar: operación que permite que todas las partes de un objeto sean accedidas en un orden bien definido
- Constructor: operación que crea un objeto e inicializa su estado
- Destructor: operación que libera el estado de un objeto y (opcionalmente) destruye el propio objeto.

### Mensajes
Los objetos se comunican mediante solicitudes. Una solicitud es un mensaje que especifica la realización de una operación con uno o más objetos como parámetros que, de manera opcional, devuelve un resultado.
Los mensajes se usan para especificar una comunicación entre objetos
![[Pasted image 20240913010217.png]]
Ejemplo:
![[Pasted image 20240913010143.png]]

Composición:
![[Pasted image 20240913010154.png]]

### Encapsulado
El empaquetamiento del conjunto de datos y métodos recibe el nombre de encapsulado.
El objeto esconde/encapsula su estructura de datos a los demás objetos y la única forma de acceder a ellos es mediante operaciones o métodos propios cuya implementación está oculta (*privada*) para el usuario.
Implica el ocultamiento de los detalles de implementación de un objeto respecto de su usuario.
![[Pasted image 20240913010624.png]]

**Ventajas:**
- Evita la interferencia con los aspectos internos
- Oculta la complejidad de sus componentes
- Evita corrupción de los datos
- Protege los datos de un uso arbitrario

### Herencia
Un tipo de objetos de alto nivel puede especializarse en sub-tipos ó tipos de objetos de niveles más bajos.
![[Pasted image 20240913010913.png]]


## Beneficios de la tecnología OO
- Reutilización: para maximizar la reutilización se construyen las clases de modo que se puedan adaptar.
- Estabilidad: las clases diseñadas para la reutilización repetida se vuelven estables.
- El diseñador piensa en términos del comportamiento de objetos y no en detalles de bajo nivel: el encapsulado oculta los detalles de implementación de las clases y hace que las clases complejas sean fáciles de utilizar
- Creciente biblioteca de tipos de objetos
- Se construyen clases cada vez más complejas: El software se crea a partir de clases ya existentes y probadas, Esto permite construir componentes complejos de software.
- Diseño de mayor calidad: ya que se integran a partir de componentes ya probados que han sido verificados y pulidos varias veces.
- Diseño más rápido
- Confiabilidad: el software construido a partir de clases estables ya probadas tiene menos fallas que el software elaborado a partir de cero.
- Integridad: las estructuras de datos sólo pueden ser utilizadas por métodos específicos.
- Programación más sencilla: los programas se conforman a partir de pequeñas piezas, cada una de las cuales se crea fácilmente
- Mantenimiento más sencillo: El mantenimiento de sistemas OO es mucho más sencillo.
	- Los eventos cambian el estado de los objetos. La mayoría de estos cambios de estados requiere pequeñas partes de código menos propensas a errores.
	- Cada objeto lleva a cabo una función específica e independiente de los demás objetos
- Modelado más realista: El análisis OO modela el área de aplicación de manera que sea lo más cercana posible a la realidad.
- Mejor comunicación entre los profesionales del sistema y los empresarios: Los empresarios comprenden más fácilmente el paradigma OO.
- Etc.



---

---
# UML