# Punto 1 y 2

#### Aulas Virtuales:
| **Usuario:**      | Simple/Comp | Almacenado/Derivado | Mono/Multi | Opcional |
| ----------------- | :---------: | :-----------------: | :--------: | :------: |
| - idUsuario       |      S      |          A          |    MONO    |    N     |
| - mail            |      S      |          A          |    MONO    |    N     |
| - clave           |      S      |          A          |    MONO    |    N     |
| - *DNI*           |      S      |          A          |    MONO    |    N     |
| - dirección       |      S      |          A          |    MONO    |    S     |
| - teléfono        |      S      |          A          |    MONO    |    S     |
| - fechaNacimiento |      S      |          A          |    MONO    |    N     |
| - rol             |      S      |          A          |    MONO    |    N     |

| **Curso:**    | Simple/Comp | Almacenado/Derivado | Mono/Multi | Opcional |
| ------------- | :---------: | :-----------------: | :--------: | :------: |
| - idCurso     |      S      |          A          |    MONO    |    N     |
| - *Programa*  |      S      |          A          |    MONO    |    N     |
| - fechaInicio |      S      |          A          |    MONO    |    N     |
| - fechaFin    |      S      |          A          |    MONO    |    N     |

#### Pandemia

| **Paciente:** | Simple/Comp | Almacenado/Derivado | Mono/Multi | Opcional |
| ------------- | :---------: | :-----------------: | :--------: | :------: |
| - idPaciente  |      S      |          A          |    MONO    |    N     |
| - DNI         |      S      |          A          |    MONO    |    N     |
| - nombre      |      S      |          A          |    MONO    |    N     |
| - dirección   |      S      |          A          |    MONO    |    S     |
| - teléfono    |      S      |          A          |    MONO    |    N     |

| **Profesional:** | Simple/Comp | Almacenado/Derivado | Mono/Multi | Opcional |
| ---------------- | :---------: | :-----------------: | :--------: | :------: |
| - idProfesional  |      S      |          A          |    MONO    |    N     |
| - *matricula*    |      S      |          A          |    MONO    |    N     |
| - nombre         |      S      |          A          |    MONO    |    S     |
| - dirección      |      S      |          A          |    MONO    |    N     |

| **Testeo:** | Simple/Comp | Almacenado/Derivado | Mono/Multi | Opcional |
| ----------- | :---------: | :-----------------: | :--------: | :------: |
| - idTesteo  |      S      |          A          |    MONO    |    N     |
| - fecha     |      S      |          A          |    MONO    |    N     |
| - lugar     |      S      |          A          |    MONO    |    N     |
| - tipo      |      S      |          A          |    MONO    |    N     |
| - resultado |      S      |          A          |    MONO    |    N     |
#### Juego de Rol

| **Personaje:** | Simple/Comp | Almacenado/Derivado | Mono/Multi | Opcional |
| -------------- | :---------: | :-----------------: | :--------: | :------: |
| - idPersonaje  |      S      |          A          |    MONO    |    N     |
| - nombre       |      S      |          A          |    MONO    |    N     |
| - salud        |      S      |          A          |    MONO    |    N     |
| - energía      |      S      |          A          |    MONO    |    N     |
| - fuerza       |      S      |          A          |    MONO    |    N     |
| - destreza     |      S      |          A          |    MONO    |    N     |
| - inteligencia |      S      |          A          |    MONO    |    N     |
| - velocidad    |      S      |          A          |    MONO    |    N     |

| **Items:**       | Simple/Comp | Almacenado/Derivado | Mono/Multi | Opcional |
| ---------------- | :---------: | :-----------------: | :--------: | :------: |
| - nombre         |      S      |          A          |    MONO    |    N     |
| - nivel          |      S      |          A          |    MONO    |    N     |
| - poder          |      S      |          A          |    MONO    |    N     |
| - durabilidad    |      S      |          A          |    MONO    |    N     |
| - categoria      |      S      |          A          |    MONO    |    N     |
| - fechaObtencion |      S      |          A          |    MONO    |    N     |
#### Salón de fiestas:

| **Cliente:** | Simple/Comp | Almacenado/Derivado | Mono/Multi | Opcional |
| ------------ | :---------: | :-----------------: | :--------: | :------: |
| - nombre     |      S      |          A          |    MONO    |    N     |
| - apellido   |      S      |          A          |    MONO    |    N     |
| - *DNI*      |      S      |          A          |    MONO    |    N     |
| - dirección  |      S      |          A          |    MONO    |    S     |
| - teléfono   |      S      |          A          |    MONO    |    S     |

| **Reserva:** | Simple/Comp | Almacenado/Derivado | Mono/Multi | Opcional |
| ------------ | :---------: | :-----------------: | :--------: | :------: |
| - fecha      |      S      |          A          |    MONO    |    N     |
| - horaInicio |      S      |          A          |    MONO    |    N     |
| - horaFin    |      S      |          A          |    MONO    |    N     |
| - monto      |      S      |          A          |    MONO    |    N     |

| **Servicio:** | Simple/Comp | Almacenado/Derivado | Mono/Multi | Opcional |
| ------------- | :---------: | :-----------------: | :--------: | :------: |
| - *tipo*      |      S      |          A          |    MONO    |    N     |
| - precio      |      S      |          A          |    MONO    |    N     |
#### Licencias de Conducir

| **Conductor:**    | Simple/Comp | Almacenado/Derivado | Mono/Multi | Opcional |
| ----------------- | :---------: | :-----------------: | :--------: | :------: |
| - apellido        |      S      |          A          |    MONO    |    N     |
| - nombre          |      S      |          A          |    MONO    |    N     |
| - *DNI*           |      S      |          A          |    MONO    |    N     |
| - domicilio       |      S      |          A          |    MONO    |    N     |
| - fechaNacimiento |      S      |          A          |    MONO    |    N     |
| - sexo            |      S      |          A          |    MONO    |    S     |
| - grupoSanguineo  |      S      |          A          |    MONO    |    N     |

| **Licencia:**      | Simple/Comp | Almacenado/Derivado | Mono/Multi | Opcional |
| ------------------ | :---------: | :-----------------: | :--------: | :------: |
| - idLicencia       |      S      |          A          |    MONO    |    N     |
| - fechaOtorgada    |      S      |          A          |    MONO    |    N     |
| - fechaVencimiento |      S      |          A          |    MONO    |    N     |
| - anteojos         |      S      |          A          |    MONO    |    N     |
| - tipoUso          |      S      |          A          |    MONO    |    N     |

| **Clase:**    | Simple/Comp | Almacenado/Derivado | Mono/Multi | Opcional |
| ------------- | :---------: | :-----------------: | :--------: | :------: |
| - *tipo*      |      S      |          A          |    MONO    |    N     |
| - descripción |      S      |          A          |    MONO    |    N     |
#### Pedidos Ya

| **Cliente:** | Simple/Comp | Almacenado/Derivado | Mono/Multi | Opcional |
| ------------ | :---------: | :-----------------: | :--------: | :------: |
| - *telefono* |      S      |          A          |    MONO    |    N     |
| - mail       |      S      |          A          |    MONO    |    N     |
| - nombre     |      S      |          A          |    MONO    |    N     |
| - direccion  |      S      |          A          |    MONO    |    N     |

| **Negocio:** | Simple/Comp | Almacenado/Derivado | Mono/Multi | Opcional |
| ------------ | :---------: | :-----------------: | :--------: | :------: |
| - nombre     |      S      |          A          |    MONO    |    N     |
| - direccion  |      S      |          A          |    MONO    |    N     |
| - telefono   |      S      |          A          |    MONO    |    N     |
| - categoria  |      S      |          A          |   MULTI    |    N     |

| **Pedido:** | Simple/Comp | Almacenado/Derivado | Mono/Multi | Opcional |
| ----------- | :---------: | :-----------------: | :--------: | :------: |
| - fecha     |      S      |          A          |    MONO    |    N     |
| - hora      |      S      |          A          |    MONO    |    N     |
| - monto     |      S      |          A          |    MONO    |    N     |


