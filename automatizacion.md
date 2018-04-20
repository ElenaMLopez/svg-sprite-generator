### ¿Cómo automatizar la creación de sprites?

Para realizar la automatización de creación de sprites, hay que poner en el módulo de scripts dle package JSON del proyecto:

``` "<comando>": "svg-sprite-generate -d images -o sprite/sprite.svg" ´´´
donde '<comando>' será el comando a utilizar en consola para arrancar la taréa de generación de sprites.

Queda algo así por ejemplo:


``` JSON
{
  "name": "sprite",
  "version": "1.0.0",
  "description": "sprite generator",
  "main": "index.js",
  "scripts": {
    "test": "echo \"Error: no test specified\" && exit 1",
    "sprite-generate": "svg-sprite-generate -d images -o sprite/sprite.svg"
  },
  "keywords": [
    "sprite"
  ],
  "author": "Elena MLopez",
  "license": "MIT"
}
```

Luego en la consola y dentro de la carpeta donde esté el proyecto:

``` npm run sprite-generate ```
Creará un sprite en la ruta sprite/sprite.svg.

**Crear un sprite nuevo sobre uno existente con imágenes nuevas**
Poner otro scrip en el JSON:
```
"add-sprite": "svg-sprite-generate -s sprite/sprite.svg -d new -o sprite/sprite.svg"
```

Al ejecutar el comando ```$ npm run add-sprite``` agregará los nuevos svg de la carpeta new al sprite que ya teníamos.
