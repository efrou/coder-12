Challenge 10 del curso de Desarrollo Móvil de Coderhouse
Para poder resolver este challenge seguir los siguientes pasos

Hacer un fork este repositorio
Una vez hecho el fork, hacer un clon copiando la URL (en el botón verde) y corriendo git clone <URL> en la consola
Una vez clonado, moverse dentro de la carpeta del proyecto y correr npm install (o yarn) para instalar las dependencias necesarias
Hacer un nuevo branch con tu nombre y apellido para identificarte (ej. git checkout -b gonzalo-aguirre)
Correr el proyecto usando expo start
Resolver el enunciado, haciendo un nuevo commit al resolver cada parte
Hacer un push del nuevo branch
Desde github.com crear un nuevo pull request desde ese branch hacia master
Enunciado
Para este challenge vamos a usar la cuenta de Firebase que creamos para el challenge anterior. Vamos a obtener un token de usuario usando Expo que nos servirá para enviarle notificaciones a ese usuario en particular.

Integrando notificaciones en Expo
Crear un archivo notifications.js donde pondremos la lógica encargada de obtener el token de Expo, usando como referencia su documentación
En lugar de enviar el token a un backend propio, guardaremos ese token del usuario en nuestra DB en Firebase, en una colección llamada tokens y usando el uid del usuario como key.
Importar el archivo notifications.js desde App.js y verificar que el token se guarda correctamente en la DB
Probando las notificaciones con la tool de Expo
Ingresar a la tool de Expo para enviar notificaciones
Obtener el token de la DB de Firebase
Hacer una prueba de una notificación, antes cerrando la app de Expo en el dispositivo
IMPORTANTE: las notificaciones no funcionan en simuladores, por lo que la prueba debe ser con un dispositivo real

Manejando las notificaciones
Para poder hacer algo ante una notificación (incluso si la aplicación ya se encuentra abierta) podemos definir un handler.

Seguir la guía de Expo
Usar un alert para mostrar el mensaje de la notificación, sin importar en qué parte de la aplicación estemos
Notar que el mensaje necesitamos pasarlo en el body de la notificación si queremos accederlo desde este handler

Identificando al usuario
Para poder mostrar el nombre del usuario más adelante, vamos a pedirle ese dato al mismo. Para eso debemos:

En la AuthLoadingScreen mostrar un <TextInput> donde el usuario ingrese su nombre y un <Button> de "Guardar"
En el onPress del <Button> guardar el nombre del usuario en la collection users usando el userId como key y { name: 'El nombre' } como valor.
Una vez guardado el dato, navegar a App
