Como hacer un juego 3D con Node.js.



Primero, ejecuta estos 5 comandos:
#1: descarga una plantilla, con, ```npx, create next app```.
#2: entra a la carpeta, con, ```cd, my game zero```.
#3: crea mas carpetas, con, ```mk, dir```.
#4: descarga estas herramientas, con, ```npm, install```.
Finalmente: ```npm, run dev```, y abre tu navegador.

Segundo.
Creemos un nuevo archivo para el menú superior. En src, /dom, agrega un nuevo componente con este código;
e importalo en el archivo, page, en la carpeta app.


Tercero.
Crea otro componente, pero, en la carpeta, módel, y agrega, un cubo 3D. de esta manera. e impórtala en la página principal.
Genial; añade más código en el componente de juego, para responder a clicks, agregar una moneda, y mostrar los puntos.
Finalmente, juegalo, en tu explorador, o telefono.













Congratulations. just by following these steps. you can easily,



  - ``` npx create-next-app@13.5 mygame0 --ts --app --src-dir --no-tailwind --eslint --import-alias "@/*" ```
  - ``` mkdir -p script src/dom src/model```
  - ``` npm i -s three @types/three @react-three/drei @react-three/fiber```
