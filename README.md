# KC-DevOps
Practica DevOps del Master KeepCoding

# Metodo de uso de la aplicación de NodeJS

Si accedemos al servidor via DNS:

http://ec2-34-230-212-167.compute-1.amazonaws.com/

Accederemos a la página de bienvenida de nuestra aplicación de Node, en ella carga la página de bienvenido a express, si por otro lado accedemos a la url:

http://ec2-34-230-212-167.compute-1.amazonaws.com/images/anuncios/bici.jpg

Accedemos al fichero estatico de una imagende una bicicleta. Los archivos estáticos están configurados para ser servidos por nginx y no por Node. Esto lo podemos comprobar gracias a la cabecera personalizado que he añadadido:

X-Owner:@MiguelArribas

Por otro lado, podemos autenticarnos en la aplicación via postman, haciendo una petición post a la URL:

http://ec2-34-230-212-167.compute-1.amazonaws.com/apiv1/users/authenticate

Incluyendo en el body de la petición:

nombre: Miguel password: 1234

Siendo nombre y password las keys, y Miguel y 1234 los valores de dichos campos

Esto nos devolverá un token de autenticación con el cual ya podemos hacer peticiones get de anuncios a la API, via navegador o via postman:

http://ec2-34-230-212-167.compute-1.amazonaws.com/apiv1/anuncios?token=eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJ1c2VyX2lkIjoiNThlNjE2YzM5ZjRhNzgzMzA0NTM4N2ExIiwiaWF0IjoxNDkxNDc0Mjk3LCJleHAiOjE0OTE2NDcwOTd9.P27E3QL0HugETC7y4ms3EbqyCPcDPxzX3QuwEofZOPA

Esto es un ejemplo podemos añadir el valor del token, sustituyendo "nuestro_token"

http://ec2-34-230-212-167.compute-1.amazonaws.com/apiv1/anuncios?token=nuestro_token

esto me devolverá todos los anuncion que figuran en la base de datos (MongoDB) de la aplicación.

El registro de nuevos usuarios lo podemos realizar en el endpoint del api:

http://ec2-34-230-212-167.compute-1.amazonaws.com/apiv1/users/

Proporcionando en el cuerpo de la petición POST: nombre, email, y password.

# Metodo de uso de la aplicación de Python/Django

Podemos acceder a la aplicación escribiendo directamente la ip del servidor:

http://34.230.212.167/

Una vez dentro veremos los post de los usuarios, podemos registrarnos, logearnos, crear post, etc... y usar cualquier otra funcionalidad de la aplicación.
