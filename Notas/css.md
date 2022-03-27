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