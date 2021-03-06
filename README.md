# CVDS_Lab05
## Comando Telnet
- Antes de poder ejecutar el comando telnet en la consola de comando de Windows, es necesario activar este servicio. Por tanto solo basta ejecutar la siguiente sentencia en el Windows Power Shell ejecutandolo como Admin. " dism /online /Enable-Feature /FeatureName:TelnetClient " 
![Activacion Comando Telnet](https://github.com/luis-amaya/CVDS_Lab05/blob/main/images/Activacion%20comando%20Telnet.PNG)

## Parte 1. Jugando a ser un cliente Http
- Realizando la conexion sincrona TCP/IP a traves de Telnet
![Capture1](https://github.com/luis-amaya/CVDS_Lab05/blob/main/images/Capture1.PNG)
- Peticion GET solicitando el recurso 'sssss/abc.html', utilizando la version 1.0 de HTTP
![Capture2](https://github.com/luis-amaya/CVDS_Lab05/blob/main/images/Capture2.PNG)
  * El codigo de error que sale es el 505 cuyo significado es: El servidor no soporta la version del protocolo HTTP utilizada en la solicitud.
  * Otros codigos de error:
    *  500 Internal Server Error: Un mesnaje de error, dado cuando una condicion inesperada fue encontrada y no otro mensaje de error especifico se puede dar.
    *  502 Bad Gateway: El servidor esta actuando como una compuerta o un proxy y recibio una respuesta invalida del servidor superior.
    *  504 Gateway Timeout: El servidor estaba actuando como una compuerta o proxy y no revicio una respuesta a tiempo del servidor superior.
    *  400 Bad Request: El servidor no puede o no procesara la solicitud debido a un aparente error de cliente.
    *  404 Not Found: El recurso solicitado no pudo ser encontrado pero puede estar disponible en el futuro.
- Nueva conexion con telnet a "www.httpbin.org" 
![Capture3](https://github.com/luis-amaya/CVDS_Lab05/blob/main/images/Capture3.PNG)
  * Obteniendo el recurso /html
![Capture4](https://github.com/luis-amaya/CVDS_Lab05/blob/main/images/Capture4.PNG)
- Contando las Palabras
![Capture5](https://github.com/luis-amaya/CVDS_Lab05/blob/main/images/Capture5.PNG)
  * GET: Es utilizado para solicitar datos de un recurso especifico.
  * POST: Es utilizado para enviar datos a un servidor para crear/actualizar un recurso.
  * Otras Peticiones:
    * PUT: Es utilizado para enviar datos a un servidor para crear/actualizar un recurso.
    * HEAD: Es casi identido a GET, pero sin el cuerpo de respuesta
    * DELETE: Elimina el recurso especificado.
    * OPTIONS: Describe las opciones de comunicacion para el recurso target.
- Utilizando curl
  * curl -v
![Capture6](https://github.com/luis-amaya/CVDS_Lab05/blob/main/images/Capture6.PNG)
  * curl -i
![Capture7](https://github.com/luis-amaya/CVDS_Lab05/blob/main/images/Capture7.PNG)
  * Diferencias entre parametros:
    * curl -v se utiliza para obtener el encabezado de la solicitud y su respuesta.
    * curl -i se utiliza para incluir el encabezado de la direccion remota en el output.
## Parte 2. Haciendo una Aplicacion Web Dinamica a Bajo Nivel
- Creacion de proyecto maven utilizando el arquetipo de aplicacion web estandar.
