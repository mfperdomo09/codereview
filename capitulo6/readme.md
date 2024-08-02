
# Capitulo 6: Programación en pares

## Objetivo

* Simular un trabajo de desarrollo en pares haciendo uso de laravel, el instructor hara de navegante y el estudiante como conductor quien llavara a cabo el desarrollo


## Instrucciones

1. Primero desde laragon iniciamos los servicios de mysql para base de datos y apache

![Logo](../images/cap6/1.png)

![Logo](../images/cap6/2.png)

2. Desde la terminal en la carpeta www correspondiente a laragon ejecutamos el siguiente comando de composer "composer create-project laravel/laravel nombre-poryecto", esperamos hasta que finalice.

![Logo](../images/cap6/3.png)


3. Ingresamos al proyecto y dentro del archivo .env descomentamos las lineas 23 a 27, en la linea 22 cambiamos el valor a mysql

![Logo](../images/cap6/4.png)

4.  En github desktop agremamos el proyecto

![Logo](../images/cap6/5.png)

![Logo](../images/cap6/6.png)

Como es proyecto no se inicializo en git vamos a dar click en "create a repository"

![Logo](../images/cap6/7.png)

Establecemos la informacion necesaria, en este caso con solo el nombre es sufuciente

![Logo](../images/cap6/8.png)

Ya agregado podemos publicar el repositorio en nuestra cuenta

5.  En la terminal ingresamos el comando "php artisan serve"

![Logo](../images/cap6/9.png)

Esto hara que se inicie un servicio local donde podremos hacer uso de la url que nos genera, dando "ctrl + click" a este nos abrira el nagedor y permitira visualizar la presentacion de laravel

6. Dentro del proyecto buscamos el archivo "UserFactory" en la ruta "database/factories"

![Logo](../images/cap6/10.png)

![Logo](../images/cap6/11.png)

Verificamos que el codigo sea el mismo, esto con el fin para generar datos de prueba en la base de datos

7. Ahora en la ruta "database/seeders" bucamos el archivo "DatabaseSeeder.php"

![Logo](../images/cap6/12.png)

![Logo](../images/cap6/13.png)

Descomentamos la linea User::Factory y elinamos el restos

8. Corremos las migraciones con los seeders para crear la base de datos e insertar los datos "php artisan migrate --seed"

![Logo](../images/cap6/14.png)

Nos preguntara si queremos crear la base de datos, escibimos "yes" y damos enter

9. Hacemos commit de los cambios y push para que suban al repositorio remoto

![Logo](../images/cap6/15.png)

10. Creamos una rama donde crearemos un listado de los usuarios

![Logo](../images/cap6/16.png)

Despues de creada la publicamos


11. Usamos el comando "php artisan make:controller UserController", esto creara un archivo controllador en la ruta "app/Http/Controllers"
donde podremos crear los metodos correspondientes.

![Logo](../images/cap6/17.png)

12. En el archivo contrlador que creamos, escribiremos el metodo index, donde primero traemos todos los registros de la tabla usuario, luego retonamos la vista la cual estaria en la ruta "views/user/" junto con todo los registro de usuarios

![Logo](../images/cap6/18.png)

13. Ahora ingresamos al archivo "web.php" el cual es el archivo de rutas o urls de accesso que generamos.

![Logo](../images/cap6/19.png)

![Logo](../images/cap6/20.png)

La ruta que se encuentra ahi, lo moficaremos para que no reciba una funcion si no un array con dos items, primero el controlador de usuario y el metodo que llamara esa ruta, en este caso el metodo index

14. Luego en la ruta de carpetas "resource/views/" creamos una carpeta "user" y dentro un archivo llamado "index.blade.php".

![Logo](../images/cap6/21.png)

De esta foma vemos que concuerda con la ruta que establecimos en el controlador "user.index"

15. En el archivo index, crearremos la siguiente estructura html5 donde por medio de un foreach recorreremos la coleccion de registros que enviamos del controlador

![Logo](../images/cap6/22.png)

16. Ahora desde el navegador recargamos la pagina y vemos que nos carga el listado de usuarios registrados

![Logo](../images/cap6/23.png)


