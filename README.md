# App de galería de fotos en Ionic con React

-> Para comenzar con la construcción de la aplicación móvil, es necesario instalar las siguientes dependencias:

`npm install @capacitor/camera @capacitor/storage @capacitor/filesystem`

Estas servirán para el control de la cámara, el almacenamiento y el sistema de archivos del dispositivo móvil

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

Las funciones presentadas son las que darán funcionamiento a la galería de fotos, con estas se podrá tomar la foto, guardarla y también eliminarla.

After the user navigates to Tab 2 (Photos), they can tap/click on the camera button to open up the device's camera. After taking or selecting a photo, it's stored permanently into the device's filesystem. When the user reopens the app at a later time, the photo images are loaded from the filesystem and displayed again in the gallery. The user can tap on a photo to be presented with the option to remove the photo.

#### Feature Overview
* App framework: [React](https://reactjs.org/)
* UI components: [Ionic Framework](https://ionicframework.com/docs/components)
  * Camera button: [Floating Action Button (FAB)](https://ionicframework.com/docs/api/fab)
  * Photo Gallery display: [Grid](https://ionicframework.com/docs/api/grid)
  * Delete Photo dialog: [Action Sheet](https://ionicframework.com/docs/api/action-sheet) 
* Native runtime: [Capacitor](https://capacitor.ionicframework.com)
  * Taking photos: [Camera API](https://capacitor.ionicframework.com/docs/apis/camera)
  * Writing photo to the filesystem: [Filesystem API](https://capacitor.ionicframework.com/docs/apis/filesystem)
  * Storing photo gallery metadata: [Storage API](https://capacitor.ionicframework.com/docs/apis/storage)

## Project Structure
* Tab2 (Photos) (`src/pages/Tab2.tsx`): Photo Gallery UI and basic logic.
* usePhotoGallery Hook (`src/hooks/usePhotoGallery.ts`): Logic encapsulating Capacitor APIs, including Camera, Filesystem, and Storage.

## How to Run

> Note: It's highly recommended to follow along with the [tutorial guide](https://ionicframework.com/docs/react/your-first-app), which goes into more depth, but this is the fastest way to run the app. 

0) Install Ionic if needed: `npm install -g @ionic/cli`.
1) Clone this repository.
2) In a terminal, change directory into the repo: `cd photo-gallery-capacitor-react`.
3) Install all packages: `npm install`.
4) Run on the web: `ionic serve`.
5) Run on iOS or Android: See [here](https://ionicframework.com/docs/building/running).
