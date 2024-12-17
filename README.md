# Hola-mundo
Es el cuarto que creo espero que sea el definitivo

Creamos el archivo del controlador
	
 	sudo nano /var/www/html/departamentos.centro.intranet/appython/app.py
  

Dentro del archivo añadimos

	def application(environ, start_response):
	    output = "<p>Hola</p>"
	    start_response('200 OK', [('Content-Type', 'text/html; charset=utf-8')])
	    return [output.encode('utf-8')]




     
Editamos un nuevo archivo en la ruta especificada, le añadimos lo que se ve en el archivo
	  
    sudo nano /etc/apache2/sites-available/python-web.conf

Añadimos dentro del archivo:

	<VirtualHost *:80>
	    ServerName departamentos.centro.intranet
	
	    WSGIScriptAlias / /var/www/html/departamentos.centro.intranet/appython/app.py
	
	    <Directory /var/www/html/departamentos.centro.intranet/appython>
	        Require all granted
	    </Directory>
	
	    ErrorLog ${APACHE_LOG_DIR}/error.log
	    CustomLog ${APACHE_LOG_DIR}/access.log combined
	</VirtualHost>


Activamos el sitio web 

    sudo a2ensite python-web

Me aseguro los permisos

	sudo chmod 755 /var/www/html/departamentos.centro.intranet/appython/app.py
    
Reiniciamos apache

    systemctl reload apache2
    sudo systemctl restart apache2

Editamos el archivo hosts y le añadimos ambas direcciones

	sudo nano /etc/hosts

Creamos un script de python que será lo que se verá en la web

	sudo nano /var/www/html/departamentos.centro.intranet/public_html/index.py
