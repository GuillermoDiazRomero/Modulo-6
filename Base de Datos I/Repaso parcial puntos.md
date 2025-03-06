2)a)
![[Pasted image 20250220132007.png]]
- Si se borra una película no sucede nada en la tabla Director, pues Director no tiene ninguna FK de Película
- Si se borra un género de la tabla Genero, al ser FK en Película se pondría en valor null por su tipo de borrado
- Si se borra un actor de la tabla Actor, no sucede nada en la tabla Película, pues en Película no hay ninguna FK de Actor
- Si se borra proyecta de la tabla Proyecta, en las tablas Sala y Película no sucede nada, pues no hay ninguna FK de Proyecta en las tablas Sala y Película.
- Si se borra un personaje de la tabla Personaje, no sucede nada en la tabla Película, pues no hay ninguna FK de Personaje en la tabla Película.
- Si se borra una película de la tabla Película, se borran todos los datos relacionados al id de esa película en la tabla Personaje, pues Película es una FK en la PK de Personaje, además que su modo de borrado es en cascada.
- No se podría cambiar el modo de borrado de CodPel ya que no puede existir una PK con valor nulo o default
- No se podría cambiar el modo de borrado de CodSala ya que no puede existir una PK con valor nulo o default

b)![[Pasted image 20250220132015.png]]
- Un actor puede actuar en 1 película tener una FK de pélicula y en una película pueden actuar varios actores porque Película tiene una FK en Actor
- Una película puede ser dirigida por 1 director ya que cuenta con una FK de Director y un director puede dirigir varias películas porque Película tiene una FK de Director
- En una película pueden aparecer muchos personajes pero un personaje solo puede aparecer en una película ya que en Personaje hay una FK de Película
- Una sala puede proyectar 1 sola vez una misma película ya que la tabla Proyecta posee una PK compuesta por la FK de Sala y de Película (lo cual impide la duplicación de PK).