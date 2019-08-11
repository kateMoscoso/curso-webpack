# curso-webpack

**Webpack** es un empaquetador para Javascript y sus amigos. Convierte módulos con dependencias en archivos estáticos que los navegadores entienden.
Nos permite empaquetar, optimizar los diferentes módulos Javascript y sus dependencia en nuestro proyecto. Es usado en proyectos basados en Javascript como: React, Vue, Angular entre otros.

## User Experience
* Se logra con una aplicación que:
* Funcione
* Sea rápida
* Cumpla sus necesidades
* Se actualice
* Responda a sus interacciones
* Producto de calidad

## Developer Experience
* Escribir aplicaciones de manera eficiente.
* Tener un código limpio.
* Aplicar tecnología para resolver sus problemas.
* Tener un conjunto de reglas y convenciones.
* Entorno de desarrollo optimizado en productividad.

## HINTS


CLI (Command Line Interface) que nos va a permitir interactuar y configurar Webpack desde la terminal.

El comando webpack tiene una bandera llamada --mode que nos permite cambiar entre los modos producción y desarrollo. Recuerda que por defecto nos pone en modo producción si no la especificamos.



##Iniciando un webpack.config
Al ir creciendo nuestra configuración de Webpack iremos agregando cada vez más banderas a nuestros comandos y terminará como una línea gigante en la terminal. ¿Cómo hacemos que esa línea sea muy pequeñita, personalizable y escalable? Por medio de un archivo llamado por defecto webpack.config.js.
Este archivo permite importar módulos usando el formato commonJS y recibe por lo menos dos configuraciones básicas, un entry y un output.

**Entry Point:** Es la ruta del archivo principal de nuestra aplicación JS a ser procesado por Webpack. Se pueden tener varios Entry Points.
**Output:** Es la ruta de salida donde va a generar nuestro bundle con todos nuestros archivos especificados como Entry Points empaquetados en uno sólo.


Por medio del uso de la bandera **--config** podemos especificar un archivo de configuración externo con el nombre que queramos en lugar del nombre por defecto webpack.config.js.


Nombre de los entry points
```
filename: 'js/[name].js'
```

## Manejo de assets con Loaders
Los Loaders son la funcionalidad que nos da Webpack para interpretar tipos de archivos no soportados de forma nativa por Javascript.

**style-loader** sirve para inyectar un tag style (el CSS) al DOM de nuestro HTML, mientras que **css-loader** sólo sirve para interpretar archivos CSS.

Los **Plugins** sirven para extender las capacidades de webpack y dar más poder a los loaders.



## HINTS

```
npm install --save--dev --save-exact webpack
npx webpack -v
npx webpack --entry ./index.js --output ./bundle.js --mode development

mini-css-extract-plugin
```

Indexar flags -- {flags}

```
npm run build:dev -- -w
```

Javascript es un lenguaje moderno en evolución, siempre agregando nuevas funciones. El problema es que al ser interpretado en el navegador, no tenemos control sobre que versión de Javascript soportan y por lo tanto que funciones.

Para poder usar Javascript moderno y tener una buena Developer Experience sin afectar la User Experience, existe Babel. **Babel** transpila nuestro código moderno de Javascript a una una versión que todos los navegadores pueden entender.

Desde la versión 7 de babel se instala con el @

## Soporte de JSX (React)
**JSX** es un lenguaje de templates para React que permite definir componentes con un código muy similar al HTML.

No existe navegador que entienda JSX porque no es un estándar, es algo especifico de React. Afortunadamente Babel puede transpilar el código JSX de nuestros archivos JS a código que el navegador.

## Soporte imágenes, fuentes y videos

Para soportar la importación de archivos binarios en nuestro código Javascript cómo lo son: fuentes, imágenes y videos, podemos usar **url-loader**.

url-loader transforma archivos a un cadena de texto base64 para que carguen dentro de nuestros archivos Javascript y así ahorrarnos un request al servidor por cada archivo transformado.

Debemos tomar en cuenta que sólo nos conviene convertir archivos pequeños, ya que archivos muy grandes podrían hacer nuestro archivo bundle muy pesado. Es por esto que la opción limit del url-loader sirve para asignar el peso máximo que un archivo puede tener para ser transformado en base64.
limit cuenta los bytes que va a tener el fichero 

No olvides instalar file-loader junto con url-loader ya que cuando se sobrepasa el limite establecido en la opción limit y el archivo no pueda ser transformado a base64, url-loader hará uso del file-loader para insertar un nombre y ruta de archivo en el lugar correspondiente.

Es una práctica común usar preprocesadores de CSS como: Sass, Less, Stylus y hasta PostCSS. Webpack permite integrar estos preprocesadores en su configuración a través de loaders, sólo ten cuidado con las peerDependencies que son dependencias que el loader espera estén instaladas previamente, como el caso de stylus para stylus-loader.

## Añadiendo un Dynamic Link Library
Mientras más librerías agregamos más lento se empiezan a volver nuestros builds, arruinando así la Developer Experience. Por suerte podemos crear una (o varias) Dynamic Link Library para acortar estos tiempos.

Una Dynamic Link Library (DLL)[https://webpack.js.org/plugins/dll-plugin/] es un conjunto de librerías comunes que no cambian frecuentemente por lo que se hace un build por adelantado de las mismas para no re-empaquetar cada vez que hacemos build de nuestra aplicación.

Beneficiando tanto la Developer Experience como la User Experience ya que el caché del navegador va a mantener una copia que solo va a cambiar cuando nosotros agreguemos o quitemos alguna dependencia, ahorrando así valiosos requests al servidor.