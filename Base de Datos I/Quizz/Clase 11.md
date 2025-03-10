# Sub consultas
Son consultas anidadas dentro de otra consulta principal. Estas subconsultas permiten realizar operaciones avanzadas como filtros, cálculos y comparaciones basadas en otros datos.

## Tipos de subconsultas
- *Escalares:* Devuelven un único valor (una sola fila y columna), se utiliza en expresiones de la consulta externa
- *Fila Única:* Devuelven una sola fila de datos, pero pueden tener varias columnas, se usan cuando se necesita un conjunto específico de valores
- *Múltiples Filas:* Devuelven varias filas de una sola columna, se utilizan con operadores (IN, ANY o ALL)
- *Correlacionadas:* Se ejecutan una vez por cada fila de la consulta externa, ya que hacen referencia a las columnas de la consulta principal.

### Escalares
![[Pasted image 20250305033937.png]]

### Múltiple Filas
![[Pasted image 20250305033951.png]]
### Correlacionadas
![[Pasted image 20250305034111.png]]

#### IN
![[Pasted image 20250305034330.png]]
#### ANY
![[Pasted image 20250305034344.png]]
#### ALL
![[Pasted image 20250305034359.png]]
#### EXIST
Verifica si la subconsulta devuelve al menos una fila. Comprueba la existencia de registros en otra tabla que cumplan cierta condición
![[Pasted image 20250305034439.png]]
## Subconsultas en UPDATE
![[Pasted image 20250305034821.png]]
![[Pasted image 20250305035017.png]]
![[Pasted image 20250305035033.png]]
## Subconsultas en DELETE

![[Pasted image 20250305035107.png]]
![[Pasted image 20250305035118.png]]
![[Pasted image 20250305035227.png]]
## Ejemplos de Algebra Relacional

**UNION:** Se usa para combinar el resultado de dos o más consulta. Las filas duplicadas se eliminan por defecto, pero se pueden incluir utilizando UNION ALL.
![[Pasted image 20250305035900.png]]
**INTERSECT:** Se usan para devolver las filas que están presentes en ambas consultas.
![[Pasted image 20250305040102.png]]
![[Pasted image 20250305040015.png]]
**EXCEPT:** devuelve las filas que están en la primera consulta pero no en la segunda
![[Pasted image 20250305040208.png]]
**DIVISION:** Se usa cuando quieres encontrar las entidades que están asociadas con todos los elementos de un conjunto. En SQL, se simula usando NOT EXISTS o GROUP BY con HAVING
![[Pasted image 20250305040312.png]]
![[Pasted image 20250305040350.png]]

# Vistas
Las vistas son consultas guardadas como objetos en la base de datos.

**Características:**
- Simplificación de Consultas: oculta la complejidad a los usuarios, proporciona acceso más sencillo a datos específicos.
- Seguridad: limita el acceso a ciertas columnas o datos sensibles
- Mantenimiento de Integridad: Permite acceder a datos actualizados sin duplicarlos, lo que ayuda a evitar inconsistencias.

**Forma de crear una vista**
```
CREATE VIEW nombre_vista AS (SELECT columnas FROM tabla WHERE condiciones)
```

**Forma de llamar a la vista**
```
SELECT * FROM nombre_vista WHERE (opcional)
```

## Ejemplos
![[Pasted image 20250305041654.png]]

**Agregación**
![[Pasted image 20250305041846.png]]

**JOIN**
![[Pasted image 20250305041958.png]]

**Combinado**
![[Pasted image 20250305042154.png]]

# Optimización
Las subconsultas pueden impactar en el rendimiento y a veces es mejor usar INNER JOIN. Ejemplo de consultas:
![[Pasted image 20250305042314.png]]
Para evaluar el rendimiento de una consulta se usa EXPLAIN ANALYZE y ver cual de las 2 conviene:
![[Pasted image 20250305042410.png]]
En este caso conviene la subconsulta