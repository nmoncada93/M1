# RESUMEN DE ACCIONES DE LAS ACTIVIDADES

-----ACTIVIDAD 4------ Gestor de paquetes

`git clone https://github.com/uoc-advanced-html-css/uoc-boilerplate.git`

`npm install` Esto instala Parcel

`npm install --save @fortawesome/fontawesome-free`

-----ACTIVIDAD 2------ Module Bundlers

`npm run build`

`npm run dev`

-----ACTIVIDADES ----- PUBLICACION WEB EN INTERNET

`git init -b main`

`git add . && git commit -m "initial commit"`

`gh repo create`




# **Los gestores de paquetes**

**<h2>Actividad 4</h2>**

1-Descarga el repositorio https://github.com/uoc-advanced-html-css/uoc-boilerplate 

2-Abre el fichero package.json con un editor de textos.

- ¿Qué dependencias ves? ¿Para qué crees que sirven? 
  
  ` "@parcel/transformer-sass": "^2.8.3",`
    Para preprocesador

    `"autoprefixer": "^10.4.13",`
    Parse CSS and add vendor prefixes to CSS rules

    `"npm-run-all": "^4.1.5",`
    A CLI tool to run multiple npm-scripts in parallel or sequential.

    `"parcel": "^2.8.3",`
    Parcel is a zero configuration build tool for the web

    `"postcss-preset-env": "^7.8.3",`
    Lets you convert modern CSS into something most browsers can understand

    `"posthtml-include": "^1.7.4",`
    `"rimraf": "^3.0.2",`
    `"sharp": "0.31.1"`
    
- ¿Qué otras entradas hay en este fichero y para qué sirven?
  
    `  "scripts": {
    "parcel:serve": "parcel src/index.html -p 8123 --target web --open",
    "parcel:build": "parcel build src/index.html --target web --no-source-maps --no-cache",
    "clean": "rimraf dist .cache .cache-loader .parcel-cache",
    "dev": "npm-run-all clean parcel:serve",
    "build": "npm-run-all clean parcel:build",
    "test": "echo 'Everything is working as expected ✅\nStart working on your project by running \\033[1mnpm run dev\\033[0m'"
  },`


3- Ejecuta el comando npm install des del terminal en tu carpeta de trabajo. 
- ¿Para qué sirve este comando?
  
  *Sirve para instalar paquetes basicos.*
- ¿Qué ocurre dentro de la carpeta cuando lo ejecutas?
  
  *Se crea la carpeta node_modules*

4- Instala una dependencia nueva en el proyecto. Te proponemos instalar FontAwesome , una conocida libería de íconos que usaremos en la siguiente sección. Para instalar esta librería, ejecuta el comando **npm install --save @fortawesome/fontawesome-free** , como se explica en esta sección de su documentación. 

- ¿Cómo afecta esta
instalación al contenido del fichero package.json ?
*Se instala este nuevo paquete:*

  `"dependencies": {
    "@fortawesome/fontawesome-free": "^6.3.0"
  }`

# **Module bundlers**

**<h2>Actividad 1</h2>**

Ahora fíjate en el contenido de la sección scripts del fichero package.json . ¿Para qué crees que sirve?

*Pienso que puede servir para las configuraciones iniciales*

**<h2>Actividad 2</h2>**

Realiza las siguientes actividades y responde las siguientes preguntas:

1- Ejecuta el comando **npm run build**
- ¿Qué ocurre en el terminal? 
  
`PS C:\UOC-HERRAMIENTAS-2\modulo-1\uoc-boilerplate> npm run build`

`> uoc-boilerplate@3.6.0 build`

`dist\index.html              965 B    970ms`

`dist\logo.67aa2f59.webp    7.16 KB     69ms`

`dist\logo.74ea10e8.png     12.9 KB    234ms`

`dist\index.7c2e8b20.css      862 B    205ms`

`dist\index.9e9614f0.js        27 B    270ms`

`dist\index.9e9614f0.js        27 B    281ms`

*Segun parece se "pre-cargan" todos estos archivos.*
  
- ¿Qué ocurre en la carpeta de trabajo? 
  
  *Se ha creado un carpeta "Dist" con archivos e imagenes en su interior.*
  
- ¿Qué crees que hay en la nueva carpeta que ha aparecido? 
  *Tal vez sean plantillas de punto de partida*
 
Inspecciona los ficheros generados. 

- ¿Qué diferencias hay con los contenidos de la carpeta src/ ? Para encontrar estas diferencias, fíjate en la estructura de los ficheros en las carpetas, el peso de los ficheros, y abre también algun fichero (por ejemplo, el index.html en ambas rutas) con tu editor de texto para compararlos.ç
  *Se puede apreciar que el HTML de Dist esta "optmizado"/"minificado??" y además ocupa menos espacio en disco duro.


2- Ejecuta el comando **npm run dev** . 
- ¿Qué ocurre? ¿Qué diferencias hay con la ejecución del comando anterior? 
  
  Mantén esta ventana del terminal abierta. Si no se te abre el navegador automáticamente (en el caso de los usuarios del subsistema de Linux para Windows, por ejemplo), abre una nueva ventana del navegador e introduce la URL que te apareció en el terminal (normalmente, http://localhost:8123 ).

  *Se abre una nueva ventana en el navegador con una plantilla de la UOC y no se crea nigún archivo nuevo a diferencia del comando anterior.*

3- Abre el fichero src/assets/styles/_variables.scss . Prueba a cambiar alguna de los códigos de color que aparecen en las
líneas 4-5 de este fichero, y observa qué ocurre en el navegador.

  *Observo que cualquier cambio que hago al guardar se pueden ver los cambios en tiempo real*

4-Ahora averigua la IP de tu máquina en tu red local (por ejemplo aquí[https://www.whatismybrowser.com/detect/what-is-my-local-ip-address] ). 


5- Con cualquier otro dispositivo que no sea tu ordenador (otro ordenador, una tablet o un teléfono), conectado a la misma red local (WiFi, ethernet), abre el navegador e introduce esta dirección IP seguida de : y el puerto que vimos anteriormente (normalmente es :8123 ). ¿Qué ocurre?

*Pienso que deberia mostrarse la web que se está ejecutando en mi servidor local pero no logra conectarse*

Puedes cancelar la ejecución del entorno de desarrollo con la combinación de teclas ctrl+c

**<h2>Actividad 3: FontAwesome</h2>**

1-Abre el fichero src/index.html con tu editor de texto. Dentro del elemento `<h1></h1>` escribe el siguiente código: `<i class="fas fa-university"></i>` .

2-Ahora hay que incorporar las dependencias de FontAwesome que instalamos anteriormente a nuestro bundle. Para hacerlo, abre el fichero src/assets/styles/main.scss y, en el lugar correspondeinte (entre las líneas 17 y 21), escribe el siguiente código: `@import "npm:@fortawesome/fontawesome-free/css/all.css";`

Tienes información más detallada en este enlace https://fontawesome.com/docs/web/setup/packages.

3-Ejecuta npm run dev . ¿Qué cambios hay en la página?

*Se ha añadido un icono al final del H1*

# **Pre y Post Procesadores de estilos**

**<h2>Actividad 1</h2>**
Abre la carpeta src/assets/styles/ de UOC Boilerplate. 

¿Cuáles de las funcionalidades de Sass estudiadas están aplicadas en estos ficheros?


- *Hay un documetno de variables*
- *Se utiliza anidación junto con los Media Querys*
- *Se usan archivos PARTIALS*
- *Se usan modulos*
 

**<h2>Actividad 2</h2>**
- ¿Qué ocurre si hay algún error sintáctico en tus hojas de estilos?
  
  *la página deja de mostrarse y me indica donde esta el Error.*

Para la ejecución del entorno de desarrollo con ctrl+c . Ejecuta el comando npm run build . 

***Al ejecutar la compilación sale el mismo error y me indica donde esta el fallo***

- ¿Se han compilado correctamente para producción los cambios que has incorporado en el proyecto?
  
  ***he tenido que corregir el fallo y volver a compilar y luego ejecutar nuevamente*** `npm run dev` 

**<h2>Actividad 3</h2>**

Lee la documentación de Parcel sobre PostCSS . 

- ¿Si quisiéramos añadir un plugin de PostCSS, qué fichero deberíamos añadir a nuestro proyecto? Lo haremos más adelante, en el módulo 4.2.
  *** Se debe instalar prrimewro el Plugin, seguidamente crear el .postcssrc***

# **Post Procesador HTML**

**<h2>Actividad 1</h2>**
Lee la documentación de Parcel sobre PostHTML . Explora el fichero .posthtmlrc . 
- ¿Para qué sirve este fichero? ¿Qué plugins hay configurados y para qué sirven?

`{
  "plugins": {
    "posthtml-include": {
      "root": "./src"
    }
  }
}`

***En este caso pewrmite incluir ficheros HTML parciales, será todos lo que estendentro de SRC****

**<h2>Actividad 2</h2>**
Explora el fichero index.html y detecta la etiqueta HTML no estándar.
- ¿Cómo crees que funciona? Ejecuta npm run dev y realiza modificaciones a los ficheros index.html y views/footer.html . 
  ***En el archivo index.html si modifico algo y guardo se carga en tiempo real los cambios, no veo ninguna etiqueta fuera de lo habitual... ***

  *** Si edito el archivo footer.html y elimino la linea
  `&copy; Universitat Oberta de Catalunya` veo que no se actualiza al guardar cambios, necesita compilarse y volver hacer el `npm run dev` y no entiendo por que...***
  

- ¿Qué ocurre? Ejecuta npm run build y explora los ficheros HTML generados. ¿Qué ha sucedido?

***No veo lo que sucede....***
