# Chatbot Web Interface
El objetivo de este trabajo es realizar un chatbot orientado al aprendizaje de conceptos de astronomía. El proyecto se divide en dos partes principales: la programación del chatbot con Rasa Open Source y el diseño de una interfaz web. Este repositorio corresponde a la parte de la implementación del sitio web.

# Sitio web
El sitio web está formado por los siguientes archivos HTML:
- index.html
- guia-usuario.html
- encuesta.html
- acerca-de.html

Los estilos y formatos de los componentes de la página web están definidos en el archivo styles.css.

Para conectar el sitio web con el chatbot, se realiza una conexión mediante websockets (canal socketIO). 
### Si los usuarios usan el mismo ordenador en el que se ejecuta el chatbot:
En el archivo _index.html_ escribir la siguiente línea:  
~~~
	socketUrl: "http://localhost:5005"  
~~~
Esto significa que el archivo HTML comunicará con el puerto 5005 del localhost, es decir, donde se ejecuta el chatbot.	

### Si los usuarios acceden desde otros dispositivos:
Para permitir que los usuarios puedan hablar con el chatbot sin tener que usar el mismo dispositivo con el que se ejecuta el proyecto de Rasa, se puede realizar la conexión con el localhost mediante un URL dinámico que apunta a él, usando la herramiento _ngrok_.
- Para hallar el URL dinámico con _ngrok_ escribir la siguiente línea en la terminal:  
~~~
	ngrok http 5005
~~~
Se obtendrá un URL que apunta al puerto 5005 del localhost, es decir, donde se ejecuta el chatbot.

- Introducir el URL dinámico en _index.html_:  
~~~
	socketUrl: "https://14e8-79-116-134-205.eu.ngrok.io"
~~~
Este URL es diferente en cada sesión, por lo que es necesario realizar este proceso cada vez que se caduca o se empieza una sesión nueva.
