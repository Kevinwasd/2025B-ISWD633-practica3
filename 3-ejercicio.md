## Esquema para el ejercicio
![Imagen](esquema-ejercicio3.PNG)

### Crear red net-wp
# docker network create net-wp

### Para que persista la información es necesario conocer en dónde mysql almacena la información.
# COMPLETAR LA SIGUIENTE ORACIÓN. REVISAR LA DOCUMENTACIÓN DE LA IMAGEN EN https://hub.docker.com/
En el esquema del ejercicio carpeta del contenedor (a) es /var/lib/mysql

Ruta carpeta host: .../ejercicio3/db

### ¿Qué contiene la carpeta db del host?
# Nada

### Crear un contenedor con la imagen mysql:8  en la red net-wp, configurar las variables de entorno: MYSQL_ROOT_PASSWORD, MYSQL_DATABASE, MYSQL_USER y MYSQL_PASSWORD
# docker run -d --name cont-mysql --network net-wp -e MYSQL_ROOT_PASSWORD=1234 -e MYSQL_DATABASE=db_wordpress -e MYSQL_USER=wp_user -e MYSQL_PASSWORD=123 -v "C:\Users\kevin\Documents\Kevin\POLITECNICA\Construcción\ejercicio3\db":/var/lib/mysql mysql:8

### ¿Qué observa en la carpeta db que se encontraba inicialmente vacía?
# Se crearon archivos

### Para que persista la información es necesario conocer en dónde wordpress almacena la información.
# COMPLETAR LA SIGUIENTE ORACIÓN. REVISAR LA DOCUMENTACIÓN DE LA IMAGEN EN https://hub.docker.com/
En el esquema del ejercicio la carpeta del contenedor (b) es /var/www/html

Ruta carpeta host: .../ejercicio3/www

### Crear un contenedor con la imagen wordpress en la red net-wp, configurar las variables de entorno WORDPRESS_DB_HOST, WORDPRESS_DB_USER, WORDPRESS_DB_PASSWORD y WORDPRESS_DB_NAME (los valores de estas variables corresponden a los del contenedor creado previamente)
# docker run -d --name cont-wordpress --network net-wp -v "C:\Users\kevin\Documents\Kevin\POLITECNICA\Construcción\ejercicio3\www":/var/www/html/ -p 9500:80 -e WORDPRESS_DB_HOST=cont-mysql -e WORDPRESS_DB_USER=wp_user -e WORDPRESS_DB_PASSWORD=1234 -e WORDPRESS_DB_NAME=db_wordpress wordpress

### Personalizar la apariencia de wordpress y agregar una entrada
<img width="1365" height="721" alt="image" src="https://github.com/user-attachments/assets/55110982-4717-4557-a0cf-8ad723a5f9a0" />

### Eliminar el contenedor y crearlo nuevamente, ¿qué ha sucedido?

# Se recuperó el sitio web

