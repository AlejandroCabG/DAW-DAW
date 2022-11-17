## P4: Servidores virtuales de Apache
1. Crea dos sitios web que compartirán IP y puerto, pero tendrán nombres DNS distintos para acceder a ellos. El nombre del primer dominio será daw.gimbernat.eug.es y el segundo tunombreyapellidos.gimbernat.eug.es, donde “tunombreyapellidos” contiene la inicial de tu nombre, el primer apellido, y la inicial de tu segundo apellido. De esta manera, si tu nombre es: Francisco Mesas Cervilla, el domino quedaría: fmesasc.gimbernat.eug.es.
* En el primer caso, **daw.gimbernat.eug.es** tendrá su directorio base en **/var/www/daw/** conteniendo una página llamada **index.html** que ponga el nombre de la clase como título con un archivo css para aplicarle estilos al título.
* En el segundo caso, acabrerag.gimbernat.eug.es tendrá su directorio base en **/var/www/acabrerag/**, conteniendo una página llamada **index.html** que contenga vuestro currículum aplicándole un estilo css para que se visualice correctamente.
Para ello, tendrás que crear un archivo de configuración (copiado de 000-default.conf) para cada uno de los dominios. Recuerda que con a2ensite puedes crear los enlaces simbólicos necesarios para añadir esta configuración a la ejecución de apache.

Primero configuramos los VirtualHosts en apache2 accediendo a las carpetas /etc/apache2/sites-available y /etc/apache2/sites-enabled:

![ConfiguracionVH](https://user-images.githubusercontent.com/113515472/202295917-055a5f0d-578d-4541-bf02-79bd868b7ad7.PNG)

Creamos un fichero de configuración copiando y modificando el archivo de configuración de un Virtual Host:

![CrearFicheroVH](https://user-images.githubusercontent.com/113515472/202296150-5ef44ab4-d85c-4a63-ab47-404ace68a41b.PNG)

![VHosts](https://user-images.githubusercontent.com/113515472/202296159-e73ba6ad-8454-4e83-bf48-5e847598cbc1.PNG)
![TreePath](https://user-images.githubusercontent.com/113515472/202295928-8d1db195-7ca6-44a9-b179-bb6a28d24eed.PNG)

Modificación de la ip, dominio y DNS:

![DNS](https://user-images.githubusercontent.com/113515472/202296041-7c1ac429-de03-4c7f-9d5e-df1a53a70d1e.PNG)
![DNS2](https://user-images.githubusercontent.com/113515472/202296065-e37dffdc-9c2d-412d-bc09-cec714692b49.PNG)

Fichero index.html con el título y estilo CSS:

![index1](https://user-images.githubusercontent.com/113515472/202296057-96ac9ecb-9286-47c5-a895-b0d21e9dff34.PNG)

Fichero index.html con el Currículum Vitae en formato Bootstrap:

![index2](https://user-images.githubusercontent.com/113515472/202296187-c1e75eeb-7912-4def-870a-174164a2a511.PNG)

Configuración de los parámetros /etc/apache2/sites-available/001-vhost.conf modificando el ServerName y el DocumentRoot:

![Parametros1](https://user-images.githubusercontent.com/113515472/202296135-1ea2c5c6-b4ae-4c6f-90cf-7bb84084b633.PNG)

Configuración de los parámetros /etc/apache2/sites-available/002-vhost.conf modificando el ServerName y el DocumentRoot:

![Parametros2](https://user-images.githubusercontent.com/113515472/202296165-7e7d8b55-b8b7-4185-bd70-7d32d7b7a12f.PNG)

Pruebas de comporación desde el mismo servidor usando wget:

![Pruebas1](https://user-images.githubusercontent.com/113515472/202296142-478ce284-8221-4e14-89a3-a6cbf1ffede4.PNG)
![Pruebas1](https://user-images.githubusercontent.com/113515472/202296212-d686be8e-211f-40a0-9e7c-baa5028f5db5.PNG)

Directorio daw.gimbernat.eug.es:

![daw](https://user-images.githubusercontent.com/113515472/202321053-fc07453b-a4f3-4b24-b35f-d1ccb7f974bf.PNG)

index.html daw.gimbernat.eug.es:

![daw_index](https://user-images.githubusercontent.com/113515472/202321065-1532b901-45cd-4b80-8256-1345be12de91.PNG)

Directorio acabrerag.gimbernat.eug.es:

![acabrerag](https://user-images.githubusercontent.com/113515472/202320846-94bd9c46-338b-47c2-9ca4-fee789c5631c.PNG)

index.html con el currículum vitae (en lugar de CSS se ha añadido bootstrap) acabrerag.gimbernat.eug.es:

![acabrera_cv](https://user-images.githubusercontent.com/113515472/202320871-bceda52a-c88d-4772-837c-644aa0e009ad.PNG)



