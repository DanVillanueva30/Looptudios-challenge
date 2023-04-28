# Frontend Mentor - Loopstudios landing page solution

This is a solution to the [Loopstudios landing page challenge on Frontend Mentor](https://www.frontendmentor.io/challenges/loopstudios-landing-page-N88J5Onjw). Frontend Mentor challenges help you improve your coding skills by building realistic projects. 

## Tabla de contenido

  - [El desafío](#el-desafío)
  - [Descripción general](#descripción-general)
  - [Links](#links)
  - [My proceso](#mi-proceso)
  - [Creado con](#creado-con)
  - [Dependencias de desarrollo](#dependencias-de-desarrollo)
  - [Lo que he aprendido](#lo-que-he-aprendido)
  - [Fuentes de información](#fuentes-de-información)
  - [Autor](#autor)



### El desafío

Los usuarios deben ser capaces de:

- Ver el diseño más óptimo del sitio dependiendo del tamaño de pantalla de su dispositivo
- Ver los hover states para todos los elementos interactivos del sitio


### Descripción general

    **Nota: La primera vez que se compila gulp se crea la carpeta build con el css minificado, las imagenes en diferentes formatos y más ligeras,

    **Nota 2: No se debe mover nada en la carpeta build, ya que ahí se encuentra todo lo que se compiló con Gulp pero, de forma manual yo creé la carpeta js y dentro de ésta el archivo js en el cual están las funciones, lo hice para no crear la carpeta por fuera y que estuviera mejor organizado.

Este landing page fue creado con HTML, Css y JavaScript, así como Gulp, con dependencias para: Hacer más ligeras las imagenes, convertirlas en diferentes formatos (avif y webp) para que así sean aún más ligeras, también para hacer más ligero nuestro archivo Css y añadir mejoras a este. El sitio fue creado pensando en el modo de desarrollo Mobile First, utilizando la metodología BEM, y para esto también se hizo uso de SASS para poder estructurar y seccionar mejor el código CSS y así hacer el código mas entendible y que se puedan realizar ajustes de manera más sencilla. Por último utilizamos una librería De JavaScript para poder utilizar imagenes background .avif y .webp la librería se encuentra en el archivo app.js dentro de la función librería.

### Links

- Solution URL: [Mi solución](https://your-solution-url.com)
- Live Site URL: [Ir al sitio](https://loopstudios-challenge-fm.netlify.app)

## My proceso

Lo primero fue crear la estructura básica del HTML para poder empezar con los estilos CSS, en mi caso me gusta crear el HTML por secciones y agregando sus estilos al mismo tiempo, por ejemplo crear el HTML para el header y darle estilos, y seguir con la siguiente sección.
La parte que más tiempo me tomó fue la parte de "creations" con las diferentes imágenes, ya que no quise agregarlas con CSS por medio de background-image así que utilicé una forma que había aprendido hace poco, si bien tuve algunos problemas una vez solucionado pude continuar con lo demás. 
Al final creé la función de JavaScript para la navegación móvil y poder terminar con el proyecto.

### Creado con

- Semantic HTML5 markup
- Gulp
- Sass
- Metodología BEM
- Flexbox
- CSS Grid
- Mobile-first workflow
- JavaScript

### Dependencias de desarrollo


Esta es la lista de dependencias de Gulp que utilicé para realizar el proyecto: 

    ** Nota: Estas dependencias deben instalarse como dependencias de desarrollo

    "autoprefixer": "^10.4.14",
    "cssnano": "^5.1.15",
    "gulp": "^4.0.2",
    "gulp-avif": "^1.0.1",
    "gulp-imagemin": "^7.1.0",
    "gulp-postcss": "^9.0.1",
    "gulp-sass": "^5.1.0",
    "gulp-sourcemaps": "^3.0.0",
    "gulp-webp": "^4.0.1",
    "postcss": "^8.3.6",
    "sass": "^1.59.3"


### Lo que he aprendido

He aprendido a cargar imagenes de diferentes tamaños desde el HTML sin tener que ocultarlas con estilos CSS lo cual es muy útil ya que este proyecto tenía imagenes para mobile y desktop, si bien se pueden agregar todas como imágenes background quise intentar esta forma, aquí dejo el código HTML que utilicé:

Con este código, estamos definiendo diferentes versiones de la misma imagen para distintos tamaños de pantalla, y especificando el tamaño que ocupará la imagen en cada caso a través del atributo sizes. Además, para aquellos navegadores que no soporten esta técnica, estamos proporcionando una imagen por defecto a través del elemento img.

    ** Puedes reutilizar este código solo cambia las rutas de tus imágenes.

```html
<picture>
        <source 
            srcset="build/img/desktop/image-fisheye.jpg 256w,
            build/img/mobile/image-fisheye.jpg 654w"
            sizes="(max-width: 767px) 100vw, 
            (min-width: 768px),and (max-width: 1199px) 50vw, (min-width: 1200px) 256px"
            type="image/jpeg"
        >
    <img loading="lazy" decoding="async" class="card__img card__bg" src="build/img/mobile/image-fisheye.jpg" lazyalt="imagen">
</picture>
```

En base a la librería de JavaScript que se utilizó para poder agregar imagenes background .avif y .webp estas son las clases que utilicé para que se cargaran de forma correcta las diferentes versiones de las imagenes

    **Nota: Propiedades como background-size, repeat, etc, se agregan en la clase donde originalmente iría la imagen si no tuviéramos que agregar otras versiones, en este caso en .header. De igual manera es importante poner cargar primero la imagen .jpg (en caso de que el navegador no soporte las otras versiones), de no hacerlo, no se cargará la imagen .jpg
```css
.header {
    background-repeat: no-repeat;
    background-size: cover;
    padding-bottom: 10rem;
}
.not-avif.not-webp .header {
    background-image: url( -- Ruta de la imagen --.jpg);
}
.webp .header  {
    background-image: url( -- Ruta de la imagen --.webp);
}
.avif .header  {
    background-image: url( -- Ruta de la imagen --.avif);
}
```

En el archivo app.js se encuentra la librería para poder utilizar las imagenes background en formato .avf y .webp, está dentro de la función librería

```js
    function libreria() {
    console.log('Lo que se encuentra adentro de esta función es la librería')
    }
```


### Fuentes de información

- [ChatGPT](https://openai.com/blog/chatgpt) - Sin lugar a dudas es una herramienta muy buena para poder mejorar tu código y ayudarte a entender partes en las que tienes dudas o como implementar/usar algo nuevo o en lo que no se tiene tanta experiencia, en mi caso, fue en la parte de cargar diferentes imagenes con diferentes formatos desde el HTML sin la necesidad de hacerlo por medio de CSS y, mostrarlas de acuerdo a los diferentes tamaños de los dispositivos.


## Autor

- Frontend Mentor - [@DanVillanueva30](https://www.frontendmentor.io/profile/DanVillanueva30)



