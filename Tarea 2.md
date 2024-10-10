Preparación del entorno: Instalación y configuración de la red. 

Instalamos y configuramos las máquinas indicadas en la topología de red, asignando manualmente 
las direcciones IP indicadas a los dispositivos correspondientes.

Preparamos el PfSense con nuestra IP.

![Imagen PfSense](Tarea2/Captura1.PNG)

Configuramos los parámetros de red de las 3 máquinas y hacemos ping para comprobar.

![Imagen Debian Server](Tarea2/Captura2.PNG)

![Imagen Windows Cliente](Tarea2/Captura3.PNG)

![Imagen Debian Cliente](Tarea2/Captura4.PNG)

Realizamos los ajustes necesarios en el router pfSense para que funcione correctamente. 
Desactivamos el servidor DHCP en la interfaz interna.

![Imagen PfSense sin DHCP](Tarea2/Captura5.PNG)

Comprobamos que la máquina Debian navega por Internet.

![Imagen Debian Server](Tarea2/Captura6.PNG)

Configuración del servidor DHCP. 

Instalamos el servidor DHCP en la máquina correspondiente. 

![Imagen Debian DHCP](Tarea2/Captura7.PNG)

Realizamos las configuraciones adicionales necesarias para que funcione el servidor DHCP. 

![Imagen Debian DHCP](Tarea2/Captura8.PNG)

Realizo las configuraciones necesarias para cumplir los siguientes requisitos: 
a. El servidor repartirá direcciones IP en el rango 10.0.XX.1 – 10.0.XX.100. 

![Imagen Debian DHCP](Tarea2/Captura9.PNG)

b. Utilizará la máscara por defecto correspondiente a esa subred. 

![Imagen Debian DHCP](Tarea2/Captura10.PNG)

c. Deberá utilizar como puerta de enlace la que corresponda según el 
diagrama de red. 

![Imagen Debian DHCP](Tarea2/Captura11.PNG)

d. Como servidor DNS preferido se utilizará el del instituto (deberás 
averiguarlo) y como alternativo el de google. 

![Imagen Debian DHCP](Tarea2/Captura12.PNG)

e. Además, se enviará a los clientes el sufijo DNS sriXX.local. 

![Imagen Debian DHCP](Tarea2/Captura13.PNG)

f. Para el cliente Ubuntu se le reservará la dirección 10.0.XX.60.

![Imagen Debian DHCP](Tarea2/Captura14.PNG)

g. Respecto a los tiempos de alquiler: 
i. El tiempo de alquiler por defecto será de 15 días para todos los 
equipos. 
ii. Nunca será superior a 30 días. 
iii. Nunca será inferior a 1 semana. 

Configuro las 3 cosas en orden:
![Imagen Debian DHCP](Tarea2/Captura15.PNG)

Reinicio el servicio y verifico que tras el reinicio está activo y en ejecución. 

![Imagen Debian DHCP](Tarea2/Captura16.PNG)

Configuración de los clientes DHCP. 
Configuramos los equipos Windows y Linux como clientes DHCP. 

![Imagen Debian DHCP](Tarea2/Captura17.PNG)

![Imagen Win DHCP](Tarea2/Captura18.PNG)

Observamos dentro del archivo adecuado del servidor si las IPs han sido asignadas. 

![Imagen Server Asig](Tarea2/Captura19.PNG)

Observamos dentro de ambos clientes que son correctos todos los parámetros enviados por el 
servidor, es decir: 
i. IP 
ii. Máscara 
iii. Puerta de enlace 
iv. DNS primario 
v. DNS alternativo 
vi. Nombre de dominio 
vii. La MAC del equipo que tiene la reserva. 

![Imagen Win DHCP](Tarea2/Captura20.PNG)

![Imagen Win DHCP](Tarea2/Captura21.PNG)

Verifico que existe conectividad entre los equipos y que además ambos equipos se conectan 
a Internet. 

![Imagen Win Pings](Tarea2/Captura22.PNG)

![Imagen Deb Pings](Tarea2/Captura23.PNG)

Funcionamiento del servicio. 

Para terminar, explico la actividad generada por el servidor isc-dhcp-server que he 
instalado y configurado y que se ha registrado en los logs del sistema por la herramienta 
Journalctl.

![Imagen Journal](Tarea2/Captura24.PNG)