# CSS :art:

## El rol de CSS
Se encarga de colores, tamaños, animaciones y el diseño, en si CSS son hojas de estilo en cascada.

Detalladamente CSS se encarga de:
  - Tamaños y tipos de fuente
  - Colores
  - Espacios
  - Margenes
  - Adaptar diseños a distintos dispositivos
  - Animaciones

La estructura general de CSS es:
```css
/*selector {
    propiedad: valor;
}*/

p{
    color: blue;
}
```
En CSS podemos implementar los estilos de dos maneras, la primera es directamente en nuestro código HTML y la otra es linkeando a un archivo externo al index o archivo HTML.
```css
/* ARCHIVO PARA LINKEAR (styles.css)*/
p{
    color: blue;
}
```
```html
<head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Mi pagina</title>
    <!-- PRIMER FORMA DE APLICAR CSS -->
    <style>
        h1{
            text-align: center;
            color: red;
        }
    </style>
    
    <!-- SEGUNDA FORMA DE APLICAR CSS (Mejor forma) -->
    <link rel="stylesheet" href="/css/styles.css">
</head>
```

Y tambien podemos hacer que los estilos carguen más rapido con la siguiente etiqueta y caracteristicas.
```html
<head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Mi pagina</title>

    <!-- PRELOAD (Cargar los estilos más rapido) -->
    <link rel="preload" href="/css/styles.css" as="style">

    <!-- SEGUNDA FORMA DE APLICAR CSS (Mejor forma) -->
    <link rel="stylesheet" href="/css/styles.css">
</head>
```

### Selectores en CSS
Podremos seleccionar uno o multiples elementos dependiendo donde pongamos nuestro selector

  - Selector de elemento
```css
/* SELECCIONA UN ELEMENTO EN BASE A LA ETIQUETA */
p{
    color: blue;
}
```
  - Selector de clase
```css
/* SELECCIONA UNA CLASE Y ES REUTILIZABLE */
.clase{
    color: blue;
}
```

  - Selector de ID
```css
/* SELECCIONA UN ID Y ES REUTILIZABLE, A COMPARACIÓN DE LAS CLASES, EL ID ES UNICO*/
#ID{
    color: blue;
}
```
  - Selector de atributo
```css
/* SELECCIONA ELEMENTOS BASADOS EN ALGÚN ATRIBUTO QUE TENGA*/
[src="atributo.jpg"]{
    color: blue;
}
```
  - Combinación de descendentes
```css
/* SELECCIONA LOS ELEMENTOS HIJOS CUYO PADRE SEA UNA CLASE O ID EN ESPECIFICO*/
.clase .elementoHijo{
    color: blue;
}
```

  - Todos los hijos
```css
/* APLICA LO MISMO A TODOS LOS HIJOS */
.clase > elemento{
    color: blue;
}
```

### Especificidad en CSS
Es como nuestro navegador mostrara el CSS de acuerdo a que tan especifico serpa el selector que hemos creado.

Ya que CSS es en cascada esto no significara que si un selector aparece después será tomado en cuento sino más bien su especificidad.
```css
/* EJEMPLO 1 GENERAL*/
p{
    color: blue;
}
p{
    color: red;
}

/* EJEMPLO 2 ESPECIFICIDAD */
p.clase{
    color: blue;
}
p{
    color: red;
}

/* EJEMPLO 3 ESPECIFICIDAD */
p#ID{
    color: blue;
}
p{
    color: red!important;
}
```

Entonces, si un elemento tiene un selector más especifico no va a importat donde haya sido delarado, CSS decidira por su especificidad.

### Fuentes externas en CSS

Dentro de CSS podemos utilizar fuentes para nuestros textos, estas fuentes pueden venir dentro de VSC o tambien de una página de fuentes, para poder establecer una fuente se hace lo sieguiente:
```html
<!-- ESTABLECEMOS EL LINK DE LA FUENTE A UTILIZAR -->
<head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Diseñador Freelancer</title>
    <!-- FUENTE -->
    <link rel="preconnect" href="https://fonts.googleapis.com">
    <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
    <link href="https://fonts.googleapis.com/css2?family=Montserrat:wght@400;700&display=swap" 
</head>
```
```css
/* DECLARAMOS LA FUENTE A UTILIZAR CON "font-family" */
body{
    font-size: 16px;
    font-family: 'Montserrat', sans-serif;
}
```

### Displays en CSS

Dentro de CSS tenemos dos tipos de displays, block o inline.
  - Block
```css
/* EL ELEMENTO SE COLOCARÁ UNO DEBAJO DEL OTRO SIN IMPORTAR SU TAMAÑO O CONTENIDO */

display: block;
```
  - Inline
```css
/* EL ELEMENTO SE POSICIONARA A LA DERECHA UNA VEZ QUE HAYA TOMADO EL ESPACIO QUE REQUIERE */

display: inline;
```

No se es necesario especificar el display en cada elemento.

### Flexbox

Flexbox fue diseñado como un modelo unidimensional para crear layouts. En flexbox solo podemos colocar y distribuir nuestros elementos en una dirección "fila (row)" y "columna (column)".

Row es aplicado por default al definir un "display: felx;". Los otros valores son: "row-reverse", "column" y "column-reverse".

Si elegimos "row-reverse" los elementos hijos se colocarán de izquierda a derecha uno junto al otro.

Si elegimos "column" o "column-reverse" los elementos se colocarán de arriba hacia abajo.

Flexbox se especializa para alinear elementos a nuestros diseños. No añade efectos de animación, ni de textos, es una tecnología utilizada únicamente para los layouts y sustituye a los floats o table-cell.

### Estilos para escribir en CSS
#### ¿BEM, Utility First o Módulos?

- BEM (Bloques, elementos y modificadores)
```css
.card{}
.card__titulo{}
.card__imagen{}
.card__boton{}
.card__boton--activo{}
```
- Utility first
Es una propiedad y valor por clase.
```css
.text-center{}
.color-red-100{}
.bg-blue-200{}
.p-2{}
.m-2{}
```
- Modulos
Definimos el contenido principla y seleccionamos cada elemento HTML.
```css
.card{}
.card h2{}
.card img{}
.card a{}
```

### Responsive web design

Se refiere a que en todos los dispositivos nuestra página web se vea de manera correcta. Cómo podemos hacer que nuestro sitio web sea responsive? Con Media Queries
```css
@media (min-width: 768px){
    /*...
    Codigo
    */...
}
@media (min-width: 992px){
    /*...
    Codigo
    */...
}
```

### CSS Box model

En CSS todo es una caja y depende de cuatro cosas: tamaño de contenido, relleno (padding), borde y margen.

Para evitarnos andar moviendo el tamaño dentro de nuestro código CSS y así llegar al tamaño exacto, lo que haremos será lo siguiente:
```css
html{
    box-sizing: inherit;
}

/* "*" Es como un selector universal*/
*, *:before, *:after{
    box-sizing: inherit;
}
```

### CSS Grid

Nos permite definis la ubicación y tamaño de nuestros elementos. Mientras en flexbox el contenido crece automáticamente, en css grid el contenido se agrupa dentro de un area definida.

Mientras que en felxbox solo podemos movernos en 1D "row o column", en CSS Grid podemos movernos en las 2D.

Algunos diseños son más fáciles en Grid y otros en flexbox

### Grid vs Flexbox

Utilizamos FLEXBOX para alinear o distribuir elementos que estarán dentro de contendeores, por ejemplo, cuando tenemos un logotipo con enlaces dentro de una barra de navegación.

Utilizamos GRID para definir el layout de nuestros sitios web, como pueden ser las columnas o contenedores de elementos.