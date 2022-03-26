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
