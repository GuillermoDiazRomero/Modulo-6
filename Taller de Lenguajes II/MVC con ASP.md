Comando para crear nuevo proyecto webAPI basado en controladores
```
dotnet new mvc -n NombreProyecto
```

Comando para no estar reiniciando la web:
```
dotnet watch
```

Para abrirlo:
```
code -r NombreProyecto
```

Nueva estructura del proyecto
![[Pasted image 20241030175046.png]]
Ahora con el controllerBase tenemos permitido generar código HTML y CSS.
La ruta establecida por defecto para los controladores es conocida como conventional route. Se la puede mapear desde el archivo program.cs en el bloque de código
![[Pasted image 20241030175435.png]]
Método Post con un formulario
![[Pasted image 20241030175541.png]]
![[Pasted image 20241030175554.png]]
Es importante que los controladores que definamos coincidan con las carpetas que están guardadas en la ruta de Views, ya que al momento de hacer los llamados para el front-end, este se mostrará directamente por pantalla con la función View().

Los archivos adentro de las carpetas de view contienen código html que puede ser editado para realizar el front-end de mi página.

Siempre se ejecutará el controlador que contenga el nombre de Home

También es importante que el método tenga exactamente el mismo nombre que el archivo .cshtml que se desea llamar:
![[Pasted image 20241030182617.png]]
![[Pasted image 20241030182628.png]]

**Razor** es el motor que nos permite insertar código basado en .NET en páginas web y tiene la extensión ".cshtml"

Forma para agregar contenido de variables en las etiquetas html:
![[Pasted image 20241030183925.png]]
![[Pasted image 20241030184010.png]]
El siguiente puede servir como idea para randomizar distinta salidas de texto en una sola etiqueta de html
![[Pasted image 20241030184036.png]]
Utilización de for para mostrar varios mensajes:
![[Pasted image 20241030184258.png]]
Utilización de un foreach para mostrar ciertos datos en varias etiquetas html
![[Pasted image 20241030184249.png]]

Etiquetas definidas para anchors:
- asp_controller: nombre del controlador
- asp-action: nombre del método de acción
- asp-route: agrega una ruta en la url para direccionar el recurso
- asp-route-"...": agrega una ruta en la url para direccionar el recurso. También se puede parametrizar.

Ejemplo de uso:
![[Pasted image 20241030184747.png]]
Ejemplo que dirige a un controlador y luego a un método determinado pasando un id como parámetro:
![[Pasted image 20241030184918.png]]Ejemplo que dirige a un controlador y luego a un método determinado pasando un id como parámetro y especifica un nombre para el parámetro enviado (*recomiendo*):
![[Pasted image 20241030185112.png]]
Etiquetas para formularios:
![[Pasted image 20241030185318.png]]
Utilizando el atributo asp-for tenemos las siguientes equivalencias de .NET
Expresión
```
<input asp-for="\<Expression Name>">
```
Equivalencia:
![[Pasted image 20241030185640.png]]

Layout del MCV Template define la estructura común de las páginas de un sitio web.
![[Pasted image 20241030185752.png]]
Los layouts se definen en la carpeta Shared la cual nos permite almacenar vistas que se comparten entre varios controladores. Por defecto vienen con los siguientes 4 nombres:
- \_Layout.cshtml: Plantilla maestra, define la estructura general de la aplicación web
- Error.cshtml: Esta plantilla aparece cuando se produce un error en la aplicación
- \_ViewImports.cshtml: Sirve para importar espacios de nombres y otros elementos comunes en todas las visstas de la aplicación
- \_ViewStart.cshtml: Esta vista se ejecuta antes de cualquier otra vista y se utiliza para establecer valores predeterminados para la aplicación web, como diseño predeterminado o el idioma.

En \_Layout.cshtml se define toda la estructura y contiene lo siguiente:
![[Pasted image 20241030190657.png]]
Dentro del archivo Layout.cshtml @RenderBody() indica el lugar donde se insertará el contenido de la vista en la plantilla maestra.
![[Pasted image 20241030190753.png]]


La carpeta wwwroot se utiliza para almacenar archivos estáticos, como HTML, CSS, JavaScript, imágenes, etc.