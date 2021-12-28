**Integrantes:**

* Carlos Díaz
* John Vasconez
* Alexis Yépez

# App de galería de fotos en Ionic con React

-> Para comenzar con la construcción de la aplicación móvil, es necesario instalar las siguientes dependencias:

`npm install @capacitor/camera @capacitor/storage @capacitor/filesystem`

*Estas servirán para el control de la cámara, el almacenamiento y el sistema de archivos del dispositivo móvil*

-> Si la aplicación se va a ejecutar en el navegador en un principio, es necesario instalar la dependencia de PWA para poder emular las funcionalidades correctamente.

`npm install @ionic/pwa-elements`

## Código fuente
1) En el archivo **Tab2.tsx** será donde se importen los componentes de ionic y se invoque la funcionalidad de los componentes que conformen esta pantalla.

![image](https://user-images.githubusercontent.com/58191417/147398127-eaac196d-ca0b-4abd-b439-a796aa9a97d2.png)

2) A diferencia de Angular, en el archivo **App.tsx** será donde se maneje el enrutamiento de la aplicación, así como también la interfaz principal de la aplicación.

![image](https://user-images.githubusercontent.com/58191417/147398187-3095707f-680b-45cd-98b0-7860c2428b5d.png)

3) Para manejar la funcionalidad de la aplicación se ha creado el hook `usePhotoGallery.ts`, este contendrá lo siguiente:
#### Llamadas a las librerias
![image](https://user-images.githubusercontent.com/58191417/147398261-44638cb5-74e8-46ed-a7c2-bc2490b909b3.png)

#### Función de captura de foto
![image](https://user-images.githubusercontent.com/58191417/147398269-492048c9-60ad-410d-9cd2-540e598672fc.png)

#### Función para guardar imagen
![image](https://user-images.githubusercontent.com/58191417/147398281-51b9e255-733a-497b-bfaf-26869c8c0d2a.png)

#### Función para eliminar imagen
![image](https://user-images.githubusercontent.com/58191417/147398293-3636e485-96bb-4f9f-bee2-ea06da13a83b.png)

*Las funciones presentadas son las que darán funcionamiento a la galería de fotos, con estas se podrá tomar la foto, guardarla y también eliminarla.*

4) Para manejar los permisos que tendrá la aplicación, debemos definir las reglas en el archivo **AndroidManifest.xml**.

![image](https://user-images.githubusercontent.com/58191417/147422668-53b6208f-cb93-4043-8fc1-07ece6ae9d6f.png)

5) Finalmente, invocamos a las funciones de tomar foto y borrar foto en los componentes que tendrán esta funcionalidad dentro de la aplicación. Esto en el archivo **Tab2.tsx**.

![image](https://user-images.githubusercontent.com/58191417/147422782-3c809918-ce0a-451f-847f-cf78161f9983.png)

## Funcionamiento de la aplicación

a) Para probar la aplicación, ejecutamos el comando `ionic serve`, este lanzará la aplicación en un servidor local y se presentará en el navegador la siguiente pantalla:

![image](https://user-images.githubusercontent.com/58191417/147422869-4764e474-7c97-48f1-8af2-aff95d7691e8.png)

b) Al dar click por primera vez en el botón de la cámara, se solicitará permiso para acceder a la misma. Una vez concedido se iniciará la cámara del dispositivo de la siguiente manera:

![image](https://user-images.githubusercontent.com/58191417/147423038-e5972279-c851-472a-bce5-fbc11e9baa32.png)

c) Al dar click en el botón, este tomará la foto, podemos elegir guardarla dando click en el **✓** o descartarla presionando la **X**

![image](https://user-images.githubusercontent.com/58191417/147422972-82e1f63f-4d6f-4b8c-bb6b-0daeffb09644.png)

d) Al abrirse la cámara, se mostrará también un botón que, al dar click en el, nos permitira agregar imágenes a la galería manualmente.

![image](https://user-images.githubusercontent.com/58191417/147427460-bb29a6d3-403c-41a2-b81f-80e10be55631.png)

*El botón abrirá el explorador de archivos del dispositivo (en este caso del ordenador) para así poder elegir la imagen que querramos subir.*

e) De esta manera la galería de fotos presentará las imagenes y fotos que se hayan almacenado

![image](https://user-images.githubusercontent.com/58191417/147427731-cdd7a9c6-69f3-4ba7-93b7-87bdf1fcc271.png)

## APK y Bundle

#### Construcción de la aplicación

I) Ejecutamos el comando `ionic build` en la raíz del proyecto para generar el directorio **build**, esta carpeta será la base para "compilar" el proyecto para cada plataforma deseada.

![image](https://user-images.githubusercontent.com/58191417/147428145-a69b14d4-c465-4309-b94d-1a0e40a1c6e7.png)

II) Una vez generado el directorio **build**, ejecutamos el comando `ionic cap add android`. Este comando creará el directorio **android** que será la aplicación como tal para la plataforma Android (si se requiere para plataforma IOS bastaría la ejecución del comando `ionic cap add ios`).

![image](https://user-images.githubusercontent.com/58191417/147428312-bb1caa15-8b53-4ff8-9995-f62349bce5c2.png)

III) Realizado esto, es posible abrir el proyecto de android directamente en el IDE Android Studio con el comando `ionic cap open android`.

#### Creación del APK 

• Dentro de Android Studio, nos dirigimos a la ruta **Build > Build Bundle(s)/APK(s) > Build APK(s)**

![image](https://user-images.githubusercontent.com/58191417/147428647-2aaaa73c-7d80-48d4-a20c-f3269f6f1a33.png)

• Comenzará un proceso de Gradle y el resultado final será el archivo **apk** de la aplicación, al cual podremos acceder desde el explorador de archivos del sistema:

![image](https://user-images.githubusercontent.com/58191417/147428986-93b7a32f-7fbf-46f7-a151-aa9cc95c1dfb.png)

#### Creación del Bundle

• Dentro de Android Studio, nos dirigimos a la ruta **Build > Build Bundle(s)/APK(s) > Build Bundle(s)**

![image](https://user-images.githubusercontent.com/58191417/147428857-326477e7-2d8c-4820-9bdb-3c7cd877f398.png)

• Comenzará un proceso de Gradle y el resultado final será el archivo **aab** de la aplicación, al cual podremos acceder desde el explorador de archivos del sistema:

![image](https://user-images.githubusercontent.com/58191417/147429034-1c991a1b-9071-4c00-9fdd-e314e7952507.png)

### Instalación en dispositivo

Una vez generado el APK, podemos instalar la aplicación en un dispositivo Android y obtendremos el mismo resultado

![image](https://user-images.githubusercontent.com/58191417/147431526-35d6d41b-7343-404e-a965-c0f2d9518c37.png)
![image](https://user-images.githubusercontent.com/58191417/147431157-f78ba697-de56-4607-8cdd-7f8fce2f0586.png)
