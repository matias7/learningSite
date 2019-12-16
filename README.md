# Guia de Instalación para Linux

## 1\. Instalar Composer

sudo apt install composer

## 2\. Instalar Laravel 

composer global require laravel/installer

## 3\. Agregar alias de laravel en .bashrc

nano ~/.bashrc

En el archivo agregar esta linea 

alias laravel='~/.config/composer/vendor/bin/laravel'

Guardar y aplicar el cambio

source ~/.bashrc

## 4\. Agregar en github la SSH key para poder hacer clone desde el sitio

Vayan a settings > SSH and GPG Keys

ssh-keygen -t rsa -b 4096 -C "YOUR_EMAIL@example.com"

Denle todo a enter, luego

eval "$(ssh-agent -s)"

ssh-add ~/.ssh/id_rsa

Finalmente obtengan la ssh key publica con el siguiente comando

cat ~/.ssh/id_rsa.pub

Copian todo, van a github seleccionan add new ssh key y lo pegan

## 5\. Hacer Fork del proyecto y luego un clone del proyecto forkeado. (preguntar dudas)

entrar a site/ y hacer

composer install

editar o crear el archivo .env con la siguiente informacion

APP_NAME=Laravel
APP_ENV=local
APP_KEY=base64:y1OEIIQxBwDgdQ8YhX74nTS+Xe4epeknUyEs+B1LSxc=
APP_DEBUG=true
APP_URL=http://localhost

LOG_CHANNEL=stack

DB_CONNECTION=mysql
DB_HOST=127.0.0.1
DB_PORT=3306
DB_DATABASE=laravel
DB_USERNAME=root
DB_PASSWORD=

BROADCAST_DRIVER=log
CACHE_DRIVER=file
QUEUE_CONNECTION=sync
SESSION_DRIVER=cookie
SESSION_LIFETIME=120

REDIS_HOST=127.0.0.1
REDIS_PASSWORD=null
REDIS_PORT=6379

MAIL_DRIVER=smtp
MAIL_HOST=smtp.mailtrap.io
MAIL_PORT=2525
MAIL_USERNAME=null
MAIL_PASSWORD=null
MAIL_ENCRYPTION=null

AWS_ACCESS_KEY_ID=
AWS_SECRET_ACCESS_KEY=
AWS_DEFAULT_REGION=us-east-1
AWS_BUCKET=

PUSHER_APP_ID=
PUSHER_APP_KEY=
PUSHER_APP_SECRET=
PUSHER_APP_CLUSTER=mt1

MIX_PUSHER_APP_KEY="${PUSHER_APP_KEY}"
MIX_PUSHER_APP_CLUSTER="${PUSHER_APP_CLUSTER}"

## 6\. Una vez hecho todo lo anterior desde site/ en su directorio clonado hacer 

php artisan serve

E ir al link que les muestra, deberia mostrarles una bienvenida de laravel
