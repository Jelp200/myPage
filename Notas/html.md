# HTML

## El rol de HTML
El lenguaje de marcas de hipertexto (HyperText Markup Language) es un componente más que importante den el desarrollo de las paginas web, podriamos decir que sin HTML no hay página web. Su sintaxis en facil y clara.

La escturcura principal de html es:
```html
<html>
    <head>
        <title>Mi página web</title>
    </head>
    <body>
        <p>Contenido de la página</p>
    </body>
</html>
```
Debemos tener en mente que HTML no es un lenguaje de programación.

De igual manera en HTML tenemos diferentes tipos de headings.
```html
<h1>Heading 1</h1>
<h2>Heading 2</h2>
<h3>Heading 3</h3>
<h4>Heading 4</h4>
<h5>Heading 5</h5>
<h6>Heading 6</h6>
```
Cuando estamos diseñando una página web es muy frecuente que todavia no tengamos texto para poder poner, es por eso que una herramienta importante es el <a href="https://lipsum.com/"> Lorem ipsum </a> el cual nos ayudara a rellenar estos espacios.

### Estructuras el contenido en HTML
Las etiquetas para poder agurpar o estructurar nuestro código son:
```html
<header>
<footer>
<nav>
<main>
<section>
<article>
<aside>
<div>
```

### Enlaces en HTML
Para poder declarar enlcaes en HTML lo que debemos hacer es incluir la siguiente etiqueta con su atributo:
```html
<a href="dirección del enlace">Titulo del enlace</a>
```

### SVG's e Imagenes en HTML
Dentro de CSS podremos utilizar vectores e imagenes, una buena herramienta para emplear inocos es <a href="https://tablericons.com/">Tabler icons</a> y para su etiqueta para implementarlas es:
```html
<img src="ruta de la imagen"> <!-- Para imagenes -->
```

### Formularios
En HTML podemos implementar formularios con la siguiente etiqueta:
```html
<form>
```