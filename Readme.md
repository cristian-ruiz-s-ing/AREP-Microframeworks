# Servidor Web 

Este es un servidor web Java construido para proporcionar funcionalidades como el manejo de solicitudes HTTP GET y POST, la entrega de archivos estáticos y la configuración de directorios de archivos estáticos.

## Funcionamiento Básico

El servidor funciona como una aplicación Java autónoma y utiliza la clase `HttpServer` de la API `java.net` para recibir solicitudes HTTP entrantes en un puerto específico (por defecto, el puerto 8080). A continuación, se describe un poco de su funcionamiento básico:

1. **Configuración Inicial**: El servidor se configura en el puerto especificado y se establece para escuchar las solicitudes entrantes.

2. **Registro de Rutas**: El servidor permite registrar rutas para los métodos HTTP GET y POST utilizando funciones lambda. Por ejemplo, se pueden registrar rutas como `/hello` y `/echo`. Cuando se recibe una solicitud que coincide con una de estas rutas, se ejecuta la función lambda correspondiente.

3. **Gestión de Solicitudes**: Cuando llega una solicitud HTTP al servidor, se llama al método `handleRequest`. Este método determina si la solicitud es un GET o POST y si coincide con alguna de las rutas registradas. En función de esto, se ejecuta la función lambda asociada o se sirve un archivo estático.

4. **Archivos Estáticos**: El servidor puede servir archivos estáticos como páginas HTML, CSS, JavaScript e imágenes. Estos archivos se almacenan en un directorio específico que se puede configurar mediante el método `setStaticFilesDirectory`.

5. **Respuestas Personalizadas**: El servidor puede responder en diferentes formatos. Si se establece la respuesta como JSON, se configurará el encabezado `Content-Type` para indicar que el contenido es de tipo JSON.



## Uso del Servidor

El servidor se puede utilizar de la siguiente manera:

Para utilizar el servidor web Java puedes interactuar con él a través del navegador o mediante herramientas de cliente HTTP, como curl o Postman. A continuación, te explicaré cómo puedes interactuar con el servidor para realizar solicitudes HTTP GET y POST y cómo acceder a archivos estáticos servidos por el servidor.

### Realizar Solicitudes HTTP GET

1. **Abrir tu Navegador Web**: Puedes usar cualquier navegador web (Chrome, Firefox, Edge, etc.) para realizar solicitudes GET al servidor web Java simple.

2. **Especificar la URL**: En la barra de direcciones del navegador, ingresa la URL del servidor seguida de la ruta que deseas acceder. Por ejemplo, si el servidor se ejecuta en tu máquina local en el puerto 8080 y has registrado una ruta GET como `/hello`, ingresa la siguiente URL:

   ```
   http://localhost:8080/hello
   ```

3. **Enviar la Solicitud**: Presiona "Enter" o "Ir" en tu navegador para enviar la solicitud GET al servidor.

4. **Ver la Respuesta**: El servidor responderá con el contenido correspondiente. En este ejemplo, recibirás "Hello, World!" como respuesta, ya que es lo que se ha registrado para la ruta `/hello`.

## Realizar Solicitudes HTTP POST

1. **Utilizar una Herramienta de Cliente HTTP**: Para realizar solicitudes POST al servidor, puedes utilizar una herramienta de cliente HTTP como curl o Postman.

2. **Ejecutar la Solicitud**: Ejecuta un comando curl o configura una solicitud POST en Postman. Por ejemplo, si el servidor ha registrado una ruta POST como `/echo`, puedes enviar una solicitud POST con datos al servidor.

    - Con curl (ejemplo en la línea de comandos):
      ```shell
      curl -X POST -d "Mi mensaje" http://localhost:8080/echo
      ```

    - Con Postman: Configura una solicitud POST a `http://localhost:8080/echo` y define los datos en el cuerpo de la solicitud.

3. **Ver la Respuesta**: El servidor responderá con el resultado de la solicitud POST, que puede ser personalizado según lo que se haya programado en la ruta `/echo`. El resultado se mostrará en la salida de la herramienta de cliente HTTP que estés utilizando.

## Acceder a Archivos Estáticos

El servidor también puede servir archivos estáticos, como páginas HTML, CSS, JavaScript e imágenes. Para acceder a estos archivos:

1. **Especificar la URL del Archivo Estático**: En la barra de direcciones de tu navegador, ingresa la URL del servidor seguida de la ruta al archivo estático que deseas acceder. Por ejemplo, si el servidor sirve archivos estáticos desde el directorio "public" y tienes un archivo HTML llamado "index.html" en ese directorio, ingresa la siguiente URL:

   ```
   http://localhost:8080/static/index.html
   ```

2. **Enviar la Solicitud**: Presiona "Enter" o "Ir" en tu navegador para acceder al archivo estático.

3. **Ver el Archivo Estático**: El servidor entregará el archivo estático solicitado, que se abrirá en tu navegador como una página web.
