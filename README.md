# Hola-mundo
Es el cuarto que creo espero que sea el definitivo



    def application(envieron, start_response):
    	output =”<p>Hola</p>
  	  start_response(‘200 OK’,[(‘Content-Type’, ‘text/html; charset=utf-8’)])
  	  return output 
     
Editamos un nuevo archivo en la ruta especificada, le añadimos lo que se ve en el archivo
	  
    sudo nano /etc/apache2/sites-availables/python-web.conf

Activamos el sitio web 

    sudo a2ensite python-web

Reiniciamos apache

    systemctl reload apache2

Editamos el archivo hosts y le añadimos ambas direcciones

	sudo nano /etc/hosts

Creamos un script de python que será lo que se verá en la web

	sudo nano /var/www/html/departamentos.centro.intranet/public_html/index.py
