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

## HINTS

```
npm install --save--dev --save-exact webpack
npx webpack -v
npx webpack --entry ./index.js --output ./bundle.js --mode development
```