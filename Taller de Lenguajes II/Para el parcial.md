# POO

Programación Orientada a Objetos en C#

## Métodos

Llamamos Método a una función que nos permite acceder a las viables declaradas dentro de una clase.

### Constructor
Es un método cuyo nombre es igual que el nombre de su "class". La declaración incluye el nombre del método y su lista de parámetros, *NO* devuelve ningún valor.
![[Pasted image 20241012222858.png]]

### Sobrecarga
Consiste en crear más de un procedimiento, constructor de instancia o propiedad en una clase con el mismo nombre y distintos tipos de argumento.
![[Pasted image 20241012222746.png]]

## Asociación
**Agregación (TIENE UN):** es una relación entre clases débil. En este tipo, el objeto contenido puede existir con independencia del objeto que lo contiene.
![[Pasted image 20241012222154.png]]
**Composición (PARTE DE):** es una relación fuerte. El objeto contenido no puede existir sin el objeto que lo contiene.
![[Pasted image 20241012222322.png]]
Ejemplo de las asociaciones:
![[Pasted image 20241012222342.png]]
![[Pasted image 20241012222349.png]]


## Nivel de Acceso

- **Miembros de Instancia:** Accesible desde un Objeto
![[Pasted image 20241012221907.png]]
Esto en el código tendría que hacer:
```
Posicion miPosicion = new Posicion();
//recien ahora puedo hacer
miPosicion.X;
```
- **Miembros Estáticos:** Accesible desde la clase
![[Pasted image 20241012222012.png]]
Esto en el código tendría que hacer:
```
Rectangulo.CaluloArea(parametro);
```

## Acoplamiento
Lo importante del acoplamiento es tener un grado de interdependencia entre módulos o clases de un sistema.
Trabajaremos haciendo teniendo un nivel bajo de acoplamiento, es decir, que cada módulo que tengamos este a cargo de una responsabilidad (que cumpla una tarea).

Una clase puede tener varios métodos pero que cumplan 1 tarea.

## S.O.L.I.D.
- Principio de Responsabilidad Única
- Principio de ABIERTO/CERRADO
- Principio de Sustitución de Liskov
- Principio de Segregación de Interfaces
- Principio de Inversión de Dependencias

*Principio de Responsabilidad Única:*
	Una clase debe tener una única responsabilidad, una sola razón para cambiar.
![[Pasted image 20241012214141.png]]

---

## Herencia ("Es un")
Es un tipo de relación donde un objeto es **CREADO** a partir de otros objetos ya existentes, obteniendo todas las características (métodos y atributos) de la clase base.
![[Pasted image 20241012214335.png]]
En código tendría la siguiente forma:
```
Class ClaseHija : ClasePadre 
{
[…] // procesos de la clase derivada 
}
```

Ejemplo con objetos:
![[Pasted image 20241012214638.png]]

---

## Polimorfismo
- En tiempo de ejecución, los objetos de una clase derivada pueden ser tratados como objetos de una clase base en lugares como parámetros de métodos colecciones o matrices.
- Las clases bases pueden definir e implementar métodos virtuales, y las clases derivadas pueden invalidarlos, lo que significa que pueden proporcionar su propia definición e implementación

**Virtual:** 
```
public virtual void Metodo(){
	//Hacer tareas
}
```

**Override (invalida):**
```
public override void Metodo(){
	//Hacer tareas
}
```

Ejemplo juntos:
![[Pasted image 20241012221148.png]]
## Encapsulamiento
- **private:** Accesible desde la propia clase
- **public:** Accesible desde cualquier lugar del programa
- **protected:** Accesible desde la propia clase y desde las clases hijas/derivadas

## Abstracción
Lo ideal es crear abstracciones que se ajusten de manera natural y coherente a la lógica del problema que estamos resolviendo.
En algunos casos, puede ser más apropiado crear abstracciones separadas para casos diferentes, en lugar de forzar una única jerarquía de clases.

### Clase abstracta
Es una clase que forzosamente se debe derivar para que se puedan crear objetos de la misma o acceder a sus miembros. Es decir, no es posible crear instancias.

En código:
```
public abstract class ClaseAbstracta{
	private int atributo;
	public double MetodoConcreto() {return 0;} 
	public abstract double MetodoAbstracto();
}
```

Si un método es abstracto ---> la clase debe ser declarada abstracta.
![[Pasted image 20241012230502.png]]

## Interfases
La **interfaz** de una clase es todo lo que podemos hacer con ella. Todos los métodos, propiedades públicas de la clase conforman su interfaz.
Toda clase tiene una **interfaz** que define que podemos hacer con los objetos de dicha clase.
Las **interfases** son un **Contrato** que obligan a las clases que las implementan a implementar los miembros definidos en el cuerpo de la **Interfaz**.

Lo mejor es tener varias interfaces específicas en vez de una sola general.
- Interfaces Específicas: Crear interfaces pequeñas y específicas que se adapten a las necesidades de los clientes
- Desacoplamiento: reduce el acoplamiento entre clases.
- Facilidad de uso

En código:
```
interface iPrinter{
	void printDocument(Document doc);
}
```

![[Pasted image 20241012230835.png]]

---

# API
**API:** Interfaz de Programación de Aplicaciones. Conjunto de reglas bien definidas que se utilizan para especificar formalmente la comunicación entre dos componentes de software.
![[Pasted image 20241014001500.png]]
Tipos de API:
- API privada (o interna): conectan diferentes componentes de software dentro de una sola organización, y o esta disponible para terceros.
- API pública: proporcionan acceso público a los datos, funciones o servicios de una organización.
- API socios: permiten que 2 o más empresas compartan datos o funcionalidad para colaborar en un proyecto.

Tipo de comunicaciones:
- *Simplex:* solo es posible la transmisión en **un sentido**, del terminal que origina la información hacia el que la recibe y procesa. Ejemplo emisoras de radio.
![[Pasted image 20241014001922.png]]
- *Semidúplex (half-duplex):* permite la transmisión en ambos sentidos de manera **alterna**. Ejemplo transmisiones hechas por radioaficionados.
![[Pasted image 20241014002025.png]]
- *Dúplex (full-duplex):* consiste en transmisión en ambos sentidos de manera **simultanea**. Esta es la más eficiente.
![[Pasted image 20241014002037.png]]
Tipo de arquitecturas:
![[Pasted image 20241014002110.png]]

## API REST

Utiliza el protocolo HTTP para obtener datos o ejecutar operaciones sobre dichos datos en diversos formatos (XML o JSON).

**Restricciones:**
- *Cliente-servidor:* las aplicaciones existentes en el servidor y el cliente deben estar separadas.
- *Sin estado:* cada requisición ejecuta solo una determinada acción.
- *Caché:* la API debe utilizar la caché para evitar llamadas recurrentes al servidor.
- *Interfaz Uniforme:* cada recurso debe tener un única Ruta.


Usos:
![[Pasted image 20241014002727.png]]

## Protocolo HTTP

HTTP (Hyper Text Transfer Protocol): la comunicación HTTP se centra en el concepto solicitud-respuesta. El cliente envía al servidor una Request HTTP para hacer algo y el servidor a su vez le devuelve al cliente una Response HTTP diciendo si puede o no hacer lo que pidió.
![[Pasted image 20241014003013.png]]
Estructura
- Verbos: GET, POST, DELETE, PUT (actualiza contenidos), HEAD (igual al GET pero solo se interesa por el código de respuesta), etc.
- URI: identifica la ruta al recurso que se hace referencia (parecido a la URL).
- HTTP Version
- Request Header: contiene la metadata de la request HTTP estructurado como pares de (*llave-valor*).
- Request Body (opcional): contenido del mensaje.
![[Pasted image 20241014003324.png]]

Query simple (concatenando parámetros):
```
www.localhost.com/Accion?parámetro1=valor1&parámetro2=valor2
```

**Codigos de error:**
- 100-199 (informativas)
- 200-299 (satisfactorias)
- 300-399 (redirecciones)
- 400-499 (errores del cliente)
- 500-599 (errores del servidor)
- 200 (OK) todo ok
- 201 (Created) objeto creado
- 204 (Non Content) objeto eliminado
- 400 (Bad Request)ocurrió un error en la solicitud
- 404 (Not Found) recurso no encontrado
- 500 (Internal server error)


Ejemplo de POST:
```
POST http://MyService/Person/ HTTP/V2.0 
Host: MyService
Content-Type: text/Json; charset=utf-8 
Content-Length: 123
{
	"Person":
		{
			"ID": 1,    
			"Name": “Pablo Paramo", 
			"Email": “pparamo@gmail.com", 
			"Country": “Argentina"  
		}
}
```

Ejemplo GET:
![[Pasted image 20241014004117.png]]

--- 
## ASP webAPI
Comprobando versiones de sdks
```
dotnet --list-sdks
```
Lista de Proyecto con webAPI
```
dotnet new --list
```
Creando Proyecto (Versión 8+) webAPI con controladores:
```
dotnet new webapi --use-controllers -o MiWebAP
```
Versión 7:
```
dotnet new webapi -n MiWebAP
```

**Middle Ware (Orden y funcionalidad):** Se ejecutan en un orden específico, lo que permite una personalización y procesamiento gradual de las solicitudes. Cada middleware realiza una tarea específica.
Ejemplos:
- Autentificación
- Autorización
- Enrutamiento
- Registro compresión y manipulación de encabezados HTTP.

![[Pasted image 20241014142250.png]]
### Controlador en ASP
Es una clase que controla las solicitudes HTTP. Los métodos públicos del controlador se denominan métodos de acción o simplemente acciones.
- Se p}ueden marcar con atributos [ApiController]
- Heredan de la clase BaseController o Controller
- Es el punto de entradas para las solicitudes HTTP
- Emiten las respuestas de las solicitudes HTTP

**Clase ControllerBase:** es la que derivamos para implementar un controlador en web API. El response será un JSON.
**Controller:** Clase de la que debemos derivar para implementar un controlador en Páginas WEB.
![[Pasted image 20241014144440.png]]

**Ruteos de recursos:**
- Enrutamiento convencional: La ruta se determina en función de convenciones que definen en plantillas de ruta que, en tiempo de ejecución, mapearán las solicitudes a controladores (clases) y acciones (métodos).
Ruteo de recurso:
```
"{controller}/{action}/{id?}"
```
	{controler} mapea el controlador
	{action} mapea el nombre de la acción
	{id?} parámetro opcional (por ?), id se usa para mapear al model de entidad
- Enrutamiento basado en *Atributos*: La ruta se determina en función de los atributos que establece en sus controladores y métodos. Estos atributos definirán la asignación a las acciones del controlador.

**Atributos o Attributes:** Se los utiliza colocando el nombre de la clase entre corchetes y anteponiéndolo a un fragmento de código.

```
[Atributo]
public class MiNuevaClase { //elementos de la clase }

[Atributo]
public void Método { //Codigo del método }
```

Ejemplo de controlador con atributos:
```
[ApiController] //Atributo que indica que es un controlador
[Route("[controller]")]   //Ruta a la que se va a direccionar el recurso
public class PronosticoDelClimaController : ControllerBase{
	//Código
}
```
![[Pasted image 20241014145957.png]]
Tabla de atributos:
![[Pasted image 20241014150016.png]]
Atributos para recuperar información de un request:
![[Pasted image 20241014150047.png]]
![[Pasted image 20241014150053.png]]
En código:
```
[ApiController] //Atributo que indica que es un controlador
[Route("[controller]")]   //Ruta a la que se va a direccionar el recurso
public class PronosticoDelClimaController : ControllerBase{
	[HttpGet]
	public IActionResult GetClimaHoy(){
		//Código que devuelva el clima
	}
}
```
	Ruta de acceso:
```
	https://localhost:5001/PronosticoDelClima/GetClimaHoy
```

Método Get con 1 parámetro:
```
[ApiController] //Atributo que indica que es un controlador
[Route("[controller]")]   //Ruta a la que se va a direccionar el recurso
public class PronosticoDelClimaController : ControllerBase{
	[HttpGet("GetClima/{fecha}")] //De esta forma reescribo la ruta
	public IActionResult GetClimaHoy(datetime fecha){
		//Código que devuelva el clima en "fecha"
	}
}
```
	Ruta (fecha = 22-11-2018):
```
	https://localhost:5001/PronosticoDelClima/GetClima/22-11-2018
```

Método Get con 2 parámetros:
```
[ApiController] //Atributo que indica que es un controlador
[Route("[controller]")]   //Ruta a la que se va a direccionar el recurso
public class PacienteController : ControllerBase
{
	[HttpGet("Buscar")]
	public IActionResult Buscar(int edad, string nombre){
		//Código que devuelva los datos del paciente
	}
}
```
	Ruta:
```
https://localhost:{PORT}/Paciente/Buscar?edad=3&nombre=Carlos
```


Atributos para recuperar información de un request:
- [FromBody] : desde el cuerpo del Request.
- [FromForm] : desde los datos en formulario en el cuerpo de un Request.
- [FromHeader] : Request desde el header del request.
- [FromeQuery] : Desde los parámetros del query string.
- [FromRoute] : Desde los datos de una ruta en el Request.

Método Post con u objeto en el cuerpo del request
```
[ApiController] 
[Route("[controller]")]
public class PacienteController : ControllerBase 
{
	[HttpGet(“Alta")] 
	public IActionResult Alta([FromBody] paciente paciente) 
	{
		//codigo que devuelve el clima 
	}
}
```

Método Get que devuelve valore:
```
[HttpGet]
public List<Producto> Get() 
{
	return new list<Producto>(); 
}
```

**IActionResult y ActionResult< T >:** es una interfaz compunmente utilizada para representar el resultado de una acción en un controlador. Esta interfaz permite que una acción devuelva una variedad de tipos de resultados.
```
[HttpGet]
public ActionResult<Producto> Get() 
{
	return Ok(Product); 
}
```

Códigos de Estado:
![[Pasted image 20241014154316.png]]
