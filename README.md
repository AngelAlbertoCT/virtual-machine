# Práctica 3
## Creación de Máquinas virtuales en Azure

![Logo](https://github.com/AngelAlbertoCT/virtual-machine/blob/main/Imagenes/Logo.png)

En esta práctica se aprende a crear unentorno de ejecución de Azure Machine Learning. Se utilizarán las herramientas que nos proporciona Azure desde la página http://portal.azure.com/ .

Lo primero será ingresar al [portal de Azure](http://portal.azure.com/) con nuestro usuario y contraseña y veremos nuestra pantalla principal del portal. 

![Imgavm](https://github.com/AngelAlbertoCT/virtual-machine/blob/main/Imagenes/Imagen1.png)

Para crear una nueva máquina virtual, podemos buscar en la barra del buscador **Máquinas virtuales** o bien seleccionarlo desde la página inicial en el apartado de **Servicios de Azure**. Ahí nos mandará a la siguiente pantalla:

![Imgavm](https://github.com/AngelAlbertoCT/virtual-machine/blob/main/Imagenes/Imagen2.png)

Ya en esa pantalla, vamos a crear una nueva máquina virtual desde el botón **+ Crear** y seleccionamos la primer opción **Máquina virtual de Azure**

![Imgavm](https://github.com/AngelAlbertoCT/virtual-machine/blob/main/Imagenes/Imagen3.png)

Hay que recordar que los requisitos mínimos que se necesitan para crear un recurso en Azure es:

* Una suscripción en Azure
* Un grupo de recursos
* Una región
* Un nombre para el recurso

Para elegir la carpeta de recursos podemos seleccionar alguna (si ya está creada anteriormente) o crear un nuevo grupo desde la opción **Crear nuevo**. Ahí debemos de nombrar nuestro grupo de recursos. En este caso la nombraremos como **Sesion4VM**. Para el nombre de la máquina virtual será **VM1**. En esta ocasión veremos que podemos trabajar con las herramientas de Azure utilizando otras regiones; para esta práctica se ocupará **(Europe) UK West**. Para el apartado **Imagen** ocuparemos el sistema operativo **Windows 10 PRO**. Para el tamaño se puede seleccionar la opción que mejor convenga al momento de conocer las reglas de negocio, pero para esta práctica se utilizará la versión estandar de menor costo. Posteriormente debemos crear un **usuario** y **contraseña** y para el apartado **Seleccionar puertos de entrada** dejaremos seleccionado únicamente la opción **RDP** (Remote Desktop Protocole). Finalmente marcaremos la casilla **Confirmo que dispongo de una licencia válida de Windows 10 con derechos de hospedaje multiinquilino.** y presionamos **Revisar y crear**.

![Imgavm](https://github.com/AngelAlbertoCT/virtual-machine/blob/main/Imagenes/Imagen4.png)
![Imgavm](https://github.com/AngelAlbertoCT/virtual-machine/blob/main/Imagenes/Imagen5.png)
![Imgavm](https://github.com/AngelAlbertoCT/virtual-machine/blob/main/Imagenes/Imagen6.png)

Esperamos a que se haga la validación correspondiente y presionaremos el botón **Crear** que se encuentra ubicado en la parte inferior izquierda de nuestra pantalla.

![Imgavm](https://github.com/AngelAlbertoCT/virtual-machine/blob/main/Imagenes/Imagen7.png)

De igual manera esperaremos a que se realice la implementación correspondiente. 

![Imgavm](https://github.com/AngelAlbertoCT/virtual-machine/blob/main/Imagenes/Imagen8.png)

El objetivo secundario de esta práctica será utilizar una máquina virtual a traves de otra máquina virtual, así que, cuando termine de completarse la implementación anterior, presionaremos el botón **Crear otra VM** y realizamos los mismos pasos que en la máquina virtual anterior modificando el nombre de la segunda máquina virtual para evitar confusiones. 

![Imgavm](https://github.com/AngelAlbertoCT/virtual-machine/blob/main/Imagenes/Imagen9.png)

Al momento de crear la segunda máquina virtual es importante mencionar que no afectará en nada si se crea desde otro grupo de recursos y si se crea en otra región puede que afecte solo un poco en cuestión del tiempo de ejecución.

Antes de finalizar la creación  de la segunda máquina virtual es importante verificar que en el apartado de **Redes** en la sección **Red virtual** esté conectado a la red que tenga el nombre del grupo de recursos y que tenga la terminación **-vnet**. En nuestro caso sería **Sesion4VM-vnet**

Al finalizar la implementación de la segunda máquina virtual, accedemos a la primer MV. Esto lo podemos hacer desde la página inicial o buscandolo desde la barra de busqueda. Para realizar la conexión presionaremos **Conectar** y seleccionamos la opción **RDP**.

![Imgavm](https://github.com/AngelAlbertoCT/virtual-machine/blob/main/Imagenes/Imagen10.png)

Al redireccionarnos a la siguiente página, presionaremos el botón **Descargar archivo RDP**.

![Imgavm](https://github.com/AngelAlbertoCT/virtual-machine/blob/main/Imagenes/Imagen11.png)

Al finalizar la descarga, necesitamos abrir el archivo con un programa que pueda ejecutar ese tipo de archivos. Para esta práctica se utilizará la aplicación **Escritorio remoto de Microsoft** que se puede descargar gratuitamente en sistemas operativos Windows utilizando **Microsoft Store** 

Al abrir la descarga con el programa (o con algún otro programa de su preferencia) nos pedirá ingresar con el usuario y contraseña que utilizamos al momento de crear nuestra máquina virtual. Al realizar este paso se cargará nuestra máquina virtual con el sistema operativo Windows funcionando.

![Imgavm](https://github.com/AngelAlbertoCT/virtual-machine/blob/main/Imagenes/Imagen12.png)

Posteriormente se tendrán que configurar y aceptar los permisos que se deseen y finalmente accederemos a nuestro escritorio de Windows ocupando la primera máquina virtual que se creó.

![Imgavm](https://github.com/AngelAlbertoCT/virtual-machine/blob/main/Imagenes/Imagen13.png)

Ahora, para corroborar que ambas máquinas virtuales se encuentren conectadas en la misma res. Para esto vamos a regresar al **Portal de Azure** y nos dirigiremos al apartado **Redes** que se encuentra en la parte izquierda de nuestra pantalla. Al estar ahí, seleccionaremos **Red virtual/subred:**

![Imgavm](https://github.com/AngelAlbertoCT/virtual-machine/blob/main/Imagenes/Imagen14.png)
![Imgavm](https://github.com/AngelAlbertoCT/virtual-machine/blob/main/Imagenes/Imagen15.png)

Finalmente del lado izquiero de nuestra pantalla, en el área de configuración, seleccionaremos la opción **Dispositivos conectados** y ahí podremos comprobar que ambas máquinas virtuales están conectadas en la misma red.

![Imgavm](https://github.com/AngelAlbertoCT/virtual-machine/blob/main/Imagenes/Imagen16.png)

Ahora, para poder abrir la segunda máquina virtual dentro de la primera, vamos a necesitar realizar la busqueda de Power Shell desde la barra de busqueda de nuestra máquina virtual y ejecutaremos la aplicación como administrador.

![Imgavm](https://github.com/AngelAlbertoCT/virtual-machine/blob/main/Imagenes/Imagen17.png)

Al abrirse la terminal, ingresaremos el siguiente comando y posteriormente presionaremos el botón ENTER de nuestro teclado: 
**mstsc /v:10.0.0.5**
En este comando estamos ingresando la I.P. de la segunda máquina virtual. 

Al realizar está acción se abrirá una nueva ventana la cual nos solicitará el usuario y contraseña de la segunda máquina virtual. Al llenar estos campos se abrirá la segunda máquina virtual dentro de la primer máquina virtual que se creó.
