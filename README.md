# Guia de Instalación para Linux
1. Instalar Composer
	sudo apt install composer
2. Instalar Laravel 
	composer global require laravel/installer
3. Agregar alias de laravel en .bashrc
	nano ~/.bashrc
	En el archivo agregar esta linea 
		alias laravel='~/.composer/vendor/bin/laravel'
	Guardar y aplicar el cambio
		source ~/.bashrc

4. Agregar en github la SSH key para poder hacer clone desde el sitio
	Vayan a settings > SSH and GPG Keys
		ssh-keygen -t rsa -b 4096 -C "YOUR_EMAIL@example.com"
	Denle todo a enter, luego
		eval "$(ssh-agent -s)"
		ssh-add ~/.ssh/id_rsa
	Finalmente obtengan la ssh key publica con el siguiente comando
		cat ~/.ssh/id_rsa.pub
	Copian todo, van a github seleccionan add new ssh key y lo pegan
	

5. Hacer Fork del proyecto y luego un clone del proyecto forkeado. (preguntar dudas)

6. Una vez hecho todo lo anterior pueden entrar a site/ dentro del directorio clonado y hacer 
	php artisan serve
	E ir al link que les muestra, deberia mostrarles una bienvenida de laravel
