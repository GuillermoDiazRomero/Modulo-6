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
# Unified Modeling Language (UML)

Sistema notacional destinado al modelado de sistemas que utilizan conceptos OO.
UML (lenguaje estándar):
- Visualizar
- Especificar (los elementos de un Sistema OO)
- Construir
- Documentar
Esto es independiente del proceso de desarrollo.

UML:
- Elementos del Lenguaje
- Relaciones entre elementos: Una relación es una conexión semántica entre los elementos y provee un camino de comunicación entre ellos.
- Diagramas

![[Pasted image 20240913151602.png]]
**+ Público**
**- Privado**
**# Protegido**
**<u>Estático</u>**

**Clases en UML**
![[Pasted image 20240925131726.png]]

**Objetos:**
![[Pasted image 20240925131845.png]]

**Mensajes (se usan para especificar una comunicación entre objetos):**
![[Pasted image 20240925131934.png]]

**Notas (son los comentarios en UML):**
![[Pasted image 20240925132112.png]]




Tipos de relaciones entre elementos:
- Dependencia
- Generalización
- Asociación

#### Generalización
Es una relación taxonómica entre un elemento más general (el padre ó supertipo) y un caso más específico de ese elemento (el hijo o subtipo).
Notación:
![[Pasted image 20240925132424.png]]
![[Pasted image 20240925132434.png]]

**Herencia en UML:**
![[Pasted image 20240925132517.png]]

#### Dependencia
Es una relación semántica entre dos elementos, en la cual un cambio en un elemento puede afectar a la semántica de otro elemento.
Notación:
![[Pasted image 20240925132942.png]]

Ejemplo:
![[Pasted image 20240925133016.png]]

#### Asociación
Es una relación estructural entre dos elementos, que describe las conexiones netre ellos.
Notación:
![[Pasted image 20240925133103.png]]

Ejemplo:
![[Pasted image 20240925133116.png]]

A su vez, tiene 3 tipos de asociaciones:
- Navegabilidad: sirve para limitar la navegación a una sola dirección.![[Pasted image 20240925133211.png]]
- Multiplicidad: denota el número de objetos que pueden participar en la relación.![[Pasted image 20240925133247.png]]
- Rol: determina el papel que juega cada uno de los elementos dentro de la relación.![[Pasted image 20240925133313.png]]

**Casos Particulares:**
- Agregación: es una relación del tipo "todo/parte" dentro de la cual una o más clases son partes de un todo. Las partes pueden pertenecer a distintos agregados.![[Pasted image 20240925133422.png]]
- Composición: Es una forma de agregación, con fuerte sentido de posesión y tiempo de vida coincidentes de las partes del conjunto.![[Pasted image 20240925133456.png]]

**Diagramas:** UML define distintos tipos de diagramas para enfocar los distintos aspectos del sistema por separado. Un diagrama es una representación gráfica de un conjunto de elementos.
- Diagramas de casos de uso.
- Diagramas de Interacción (secuencia o colaboración).
- Diagramas de Clases.
- Diagramas de Objetos.

#### Diagrama de Interacción
Consisten en un conjunto de objetos y sus relaciones, incluyendo los mensajes que se pueden enviar entre ellos
- Diagrama de Secuencia: Resaltan la **ordenación temporal** de los mensajes que se intercambian.
![[Pasted image 20240925134105.png]]

- Diagrama de Colaboración/Comunicación: Resaltan la **ordenación estructural** de los objetos que envían y reciben mensajes.
![[Pasted image 20240925134122.png]]

#### Diagrama de Clases
Describe los tipos de objetos presentes en el sistema y los distintos tipos de relaciones estáticas existentes entre ellos.
![[Pasted image 20240925134351.png]]

#### Diagramas de Objetos
Ilustra un conjunto de objetos y sus relaciones en un determinado momento.
![[Pasted image 20240925134447.png]]



---

---
## Pasos para encontrar la solución a un problema mediante POO

1. Identificar datos E/S (entrada y salida), acciones requeridas y limitaciones/restricciones existentes en la descripción del problema.
2. Definir las clases que se deben implementar.
	- Identificar las posibles clases buscando los sustantivos relevantes que no sean datos de E/S.
	- Relacionar los sustantivos con los datos de E/S y las acciones identificadas.
	- Seleccionar como clases aquellos sustantivos que tienen asignado al menos un dato o al menos una acción. Los demás sustantivos son eliminados.
	- Nombrar cada clase con un sustantivo en singular y diagramarla con las variables, los métodos y sus respectivos modificadores de acceso.
3. Establecer las relaciones existentes entre las clases
4. Construir Diagrama de Clases

Ejemplo:

**PASO 1:**
![[Pasted image 20240925140733.png]]
![[Pasted image 20240925140748.png]]
![[Pasted image 20240925140800.png]]![[Pasted image 20240925140805.png]]![[Pasted image 20240925140813.png]]


**PASO 2:**
![[Pasted image 20240925140839.png]]
![[Pasted image 20240925140916.png]]
![[Pasted image 20240925140928.png]]![[Pasted image 20240925140934.png]]![[Pasted image 20240925140943.png]]![[Pasted image 20240925140949.png]]

**PASO 3:**
![[Pasted image 20240925141014.png]]

**PASO 4:**
![[Pasted image 20240925141035.png]]
![[Pasted image 20240925141052.png]]
