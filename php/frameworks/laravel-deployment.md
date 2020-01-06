# Software Utilizado
Para elaborar esta guía se utilizó
- Ubuntu 18.04 LTS.
- PHP 7.0.
- Servidor apache2.
- MySQL 5.7.
- Composer 1.9.1.

# Despliegue de Laravel desde un repositorio

1. Clonar el proyecto.
```shell
$ git clone <url_repositorio>
```

2. Ingresar a la carpeta del proyecto clonado y actualizar las dependencias mediante la utilización del **composer**:
```shell
$ composer update
```

3. Cambiar los permisos de la carpeta "storage" y "bootstrap/cache". Esto permitirá que el servidor pueda hacer uso de estas carpetas para la ejecución:
```shell
$ sudo chgrp -R www-data storage bootstrap/cache
$ sudo chmod -R ug+rwx storage bootstrap/cache
```

4. Luego cambiar los permisos de la carpeta "public". Esta carpeta debe ser accesible ya que todo el material de uso publico se encuentra en el.
```shell
$ sudo chmod -R +r public
```

5. Crear el archivo .env que es ignorado por git. Para eso hay que duplicar el archivo que se llama ".env~" y renombrarlo como ".env":
```shell
$ cp .env~ .env
```

6. Luego se ejecutan dos comandos necesarios para generar una clave única dentro de la aplicación (necesaria para ejecutar) y limpiar cualquier configuración residual que pueda haber traído el proyecto desde el repositorio:
```shell
$ php artisan key:generate
$ php artisan config:clear
```
