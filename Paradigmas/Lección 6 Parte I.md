# Relaciones entre clases

**Generalización (ES UN)**: Una clase hereda los datos y métodos de sus clases  base. Concepto básico de POO que conforma la jerarquía de clases. Un objeto de la clase derivada puede ser tratado como un objeto de la clase base

**Asociación (TIENE UN)**: Un objeto se configura como una colección o agregación de otros objetos. Se pueden construir objetos complejos utilizando otros objetos (anidamiento de clases). En C++ la asociación se Objetos puede ser en tiempo de compilación o en tiempo de ejecución.

**Dependencia (USA UN - CONOCE UN)**: Un cambio en un elemento puede afectar a la semántica de otro elemento. Un objeto usa otro objeto cuando emite una llamada o función miembro de otro objeto. Tiene conocimiento de ese objeto pero no forma parte de su estructura.

## Asociación
Establece que una clase puede tener otras clases de otros miembros. La clase se denomina *Clase contenedora* y las partes son los objetos que contiene.
![[Pasted image 20241023154655.png]]
Existen 2 tipos de Asociación:
- Agregación: Relación del tipo "todo/parte" dentro de la cual una o más clases son partes de un todo. Las partes pueden pertenecer a distintos agregados
![[Pasted image 20241023155044.png]]
![[Pasted image 20241023155034.png]]
- Composición: Relación con fuerte sentido de posesión y tiempo de vida coincidentes de las partes con el conjunto. Las partes son construidas por el todo. El todo es responsable de eliminar las partes.
![[Pasted image 20241023155135.png]]
![[Pasted image 20241023155145.png]]

Ejemplo Agregación en UML:
![[Pasted image 20241023155222.png]]Ejemplo de Composición en UML:
![[Pasted image 20241023155419.png]]
Ejemplo de Composición y Agregación en UML:
![[Pasted image 20241023160826.png]]

---
---

## En C++

### Composición

Inicialización del objeto
Composición en tiempo de Compilación:
![[Pasted image 20241023161410.png]]
Cambiando datos de la fecha de nacimiento con un método adentro del objeto
Composición en tiempo de Ejecución:
![[Pasted image 20241023161606.png]]
Eliminación del objeto persona
![[Pasted image 20241023161704.png]]
