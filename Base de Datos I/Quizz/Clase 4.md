# Modelo relacional

Un esquema conceptual es una descripción de *alto nivel* de la estructura de la Base de Datos, independiente del SGBD.

**Diseño Lógico**: Es la etapa en la que se transforma el esquema conceptual en un esquema lógico que utilizará las estructuras de datos del modelo de Base de Datos que usa el *SGBD* que se vaya a utilizar. El objetivo es transformar el esquema conceptual en un modelo de datos para ser implementado en un Sistema de Gestión de Bases de Datos (*SGBD* o *DBMS*), es decir, el modelo lógico depende del tipo de SGBD que se utiliza y no del producto concreto.

Problema --> Modelo Conceptual --> Modelo lógico --> Modelo Físico --> Base de Datos

## Modelo relacional (MR)
Se basa en la lógica de predicados y en la teoría de conjuntos. Es el paradigma del modelado de base de datos. Tiene 2 objetivos:
- **Independencia Física:** El modo de cómo se almacenan los datos no debe influir en la manipulación de la lógica, los usuarios no necesitan modificar sus programas por cambios en el almacenamiento físico.
- **Independencia Lógica:** Añadir, eliminar o modificar cualquier elemento de la BD no debe repercutir en los programas y/o usuarios que estan accediendo a subconjuntos parciales de los mismos.
- **Flexibilidad:** Ofrecer a cada usuario los datos de la forma más adecuada a la correspondiente aplicación.
- **Uniformidad:** Las estructuras lógicas de los datos presenta un aspecto uniforme (tablas), lo que facilita la concepción y manipulación de la BD por parte de los usuarios.
- **Sencillez:** Las características anteriores, así como unos lenguajes de usuario muy sencillos, producen como resultado que el modelo relacional (MR) sea fácil de comprender y de utilizar por parte del usuario final.

**Características (MR):**
- Sólida fundamentación teórica
- Independencia de la interfaz de usuario

**Generaciones de DBMS**
- Pre relacional (1° generación)
- Relacional (2° generación)
- Post relacional

**Aspecto de los datos:**
- Estructura de datos (Componentes estáticos)
- Integridad de los datos (Componentes estáticos)
- manipulación de los datos (Componentes dinámicos)

**Estructura de los Datos:**
- Relación o Tabla = Tabla
- Atributo = columna de una tabla
- Dominio = valores que toma un atributo
- Tupla o Registro = fila de una tabla

En el modelo relacional, las relaciones o tablas se utilizan para almacenar información sobre los objetos que se representan en la base de datos
![[Pasted image 20250304194843.png]]

### Conceptos
- *Tupla:* Los elementos de una relación son las tuplas o filas de la tabla. Las tuplas de una relación no siguen ningún orden. Una tupla es una fila de una relación. Conceptualmente constituye un: individuo, ejemplar u ocurrencia.
- *Grado:* El grado de una relación es el número de atributos que contiene. El grado de una relación no cambia con frecuencia.
- *Cardinalidad:* La cardinalidad de una relación es el número de tuplas que contiene. Ya que en las relaciones se van insertando y borrando tuplas a menudo, la cardinalidad de las mismas varía constantemente
- *Claves Candidatas:* El atributo o conjunto de atributos K de la relación R es una clave candidata para K si y sólo si satisface las siguientes propiedades
	- Unicidad: nunca hay 2 tuplas con mismo valor de K.
	- Irreductibilidad: no se pueden eliminar componentes de k sin destruir la unicidad.
- *Clave Primaria (PK):* Es aquella clave candidata que se escoge para identificar sus tuplas de modo único. Ya que una relación no tiene tuplas duplicadas, siempre hay una clave candidata y la relación siempre tiene clave primaria
- *Clave Ajena (FK):* Una clave ajena es un atributo o un conjunto de atributos de una relación cuyos valores coinciden con los valores de la clave primaria de alguna otra relación (puede ser la misma). Las claves ajenas representan relaciones entre datos.

#### Notación
![[Pasted image 20250305012724.png]]
![[Pasted image 20250305012745.png]]
### Restricciones Inherentes Intrínsecas
En el caso del MR, una relación tiene unas propiedades intrínsecas y que se derivan de la misma definición matemática de relación, ya que al ser un conjunto:
- No pueden haber dos tuplas iguales, obligatoriedad de la clave primaria
- El orden de las tuplas no es significativo.
- El orden de los atributos no es significativo.
- Cada atributo solo puede tomar un único valor del dominio subyacente. No se admiten grupos repetitivos.
- Ningun atributo que forme parte de la clave primaria de una relación puede tomar un valor nulo
- Si un atributo es desconocido entonces es *nulo*. Implica ausencia de información

### Restricciones Semánticas
- Son definidas por el usuario
- El modelo ofrece a los usuarios facilidades para que puedan reflejar en el esquema la semántica del mundo real.

Tipos de restricciones semánticas permitidos en el MR son:
- Clave Primaria **(PRIMARY KEY)**: declara un atributo como clave primaria, sus valores no se pueden repetir ni se admitirán nulos. En la semántica, el usuario elige que atributos forman parte de la clave primaria mientras que en la inherente define la clave primaria
- Unicidad **(UNIQUE)**: los valores de un conjunto de atributos no pueden repetirse en una relación. Permite la definición de claves candidatas (alternativas).
- Obligatoriedad **(NOT NULL)**: los atributos no admiten valores nulos
- Integridad Referencial **(FOREIGN KEY)**: 
	Si una relación R2 tiene una Clave Ajena (CA) que referencia a una clave candidata CC de la R1, todo valor de la CA debe coincidir con un valor de CC o ser nulo. 
	R2\*CA = R1\*CC.
	R1 y R2 no necesariamente son distintas.
	La CA puede ser parte de la clave primaria de R2.
	CA puede admitir nulos o tener restricción de obligatoriedad
	Además de definir las claves ajenas, hay que tener en cuenta las consecuencias operacionales
![[Pasted image 20250305015921.png]]
- Verificación **(CHECK)**: El usuario formula una condición mediante un predicado definido sobre un conjunto de atributos, tuplas o dominios, que debe ser verificado en toda operación de actualización para que el nuevo estado constituya una ocurrencia válida del esquema. Si no cumple la condición rechaza la operación.


## Transformación ER a MR
**Algoritmo de Siete Pasos:**
1. Representación de las Entidades Fuertes
2. Conversión de las entidades Débiles
3. Representaciones de las relaciones *1:1* (agrego como atributo la PK de alguno)
4. Representaciones de las relaciones *1:N* (agrego como atributo FK la PK del de grado N)
5. Representaciones de las relaciones *M:N* (creo una tabla con FK de las PK de las 2 tablas)
6. Conversión de atributos multivaluados (creo una tabla con FK de la PK de la entidad)
7. Representación de relaciones n-arios R, con n>2 (NO USAMOS ESTO)

Para las generalizaciones:
![[Pasted image 20250305031045.png]]
![[Pasted image 20250305031152.png]]

## Evolución del Modelo
1. Regla de información
2. Regla de acceso garantizado
3. Tratamiento sistemático de valores nulos
4. Catálogo en línea
5. Sub lenguaje de datos completo
6. Actualización de vistas
7. Inserción, modificación y borrado de tuplas de alto nivel
8. Independencia física de los datos
9. Independencia lógica de los datos
10. Independencia de la integridad
11. Independencia de la distribución
12. Regla de no subversión