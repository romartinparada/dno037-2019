# Diseño y Nuevos Medios → Clase 8  

### Miércoles 24 de abril → JSON & jQuery

#### JSON

[JSON (JavaScript Object Notation)](https://www.json.org/json-es.html) es un formato de texto sencillo para el intercambio de datos. 

La clase [recién pasada](https://github.com/profesorfaco/dno037-2019/tree/gh-pages/clase-07) revisamos cómo funcionan las variables en JS. Llegamos hasta un ejemplo donde una variable de nombre `a` contenía un arreglo con dos objetos.

```
var a = [{ name: "Sergey Prokopyev", craft: "ISS" }, { name: "Alexander Gerst", craft: "ISS" }];
```

Ahora noten la diferencia del ejemplo recién escrito con el que sigue: 

```
var a = JSON.parse('[{ "name": "Sergey Prokopyev", "craft": "ISS" }, { "name": "Alexander Gerst", "craft": "ISS" }]');
```

Básicamente, el único cambio está en que los denominadores `name`, y `craft` se presentan entre comillas. Cuando se presentan de tal manera ya no tenemos objetos en Javascript. Lo que tenemos es JSON, y por eso se hace necesario utilizar el método [JSON.parse](https://developer.mozilla.org/es/docs/Web/JavaScript/Referencia/Objetos_globales/JSON/parse)

Siendo JSON un formato de texto sencillo para el intercambio de datos, lo más lógico es que tenga cierta independencia; podemos dársela si lo compartimos de modo independiente, como en: https://api.myjson.com/bins/unf1s

Luego, si necesitamos ir por esos datos, para *parsearlo* en una variable de JavaScript de nombre `a`, para que luego se muestren en la consola, tendríamos que escribir: 

```
var request = new XMLHttpRequest();
request.open('GET', 'https://api.myjson.com/bins/unf1s', true);
request.onload = function () {
  var a = JSON.parse(this.response);
  console.log(a);
}
request.send();	
```

Pero el asunto se simplificaría si usamos jQuery:

```
$.getJSON('https://api.myjson.com/bins/unf1s', function(a) {
  console.log(a);
});
```

#### jQuery

jQuery es una [biblioteca](https://es.wikipedia.org/wiki/Biblioteca_(informática)) de JS que simplifica:

- la manipulación del DOM; 

- el manejo de eventos;

- el desarrollo de animaciones; y 

- el uso de [AJAX](https://www.codementor.io/sheena/ajax-tutorial-web-development-du107rzaq) (Asynchronous JavaScript And XML; una tecnología que permite a una página web actualizarse de forma dinámica sin que tenga que cargarse completamente).

jQuery se puede incluir o vincular a una página web entre etiquetas `<script></script>`. Y funcionará sí y sólo sí ya ha sido vinculada la biblioteca correspondiente: 

```
<script src="https://ajax.googleapis.com/ajax/libs/jquery/3.3.1/jquery.min.js"></script>
<script>
  //Aquí puedes usar JS simplificado por jQuery
</script>
```

Luego, para utilizar los atajos que ofrece esta biblioteca hay que recordar que, en una oración, el sujeto es quien realiza la acción o de quien se dice algo. Mientras que el predicado describe la acción que realiza el sujeto o lo que se dice del sujeto. Habiendo recordado eso, será fácil comprender qué puede resultar de esto: 

```$("sujeto").predicado();```

Así, por ejemplo, podemos escribir `$(".test").hide()` para indicar que queremos esconder (*hide*) a todos los elementos con clase `test`. ¿Pero bajo qué condiciones esconderlos? Esa condición aún no la definimos, y podríamos hacerlo repitiendo la estructura de la oración:
 
```
$("button").click(function(){
  $(".test").hide(1000);
});
```

Allí tenemos dos "oraciones". La primera tiene como sujeto a cualquier botón (*button*) y la segunda tiene como sujeto a cualquier elemento de clase *test*. El predicado de la primera es "hacer click" (*click*), mientras el predicado de la segunda es "esconder" (*hide*). Si nos fijamos en los paréntesis `({` y `})`, podemos notar que la segunda oración depende de la primera, con lo que se realizará la acción de la segunda una vez se realice la acción de la primera.

A propósito de paréntesis, una recomendación: Escribir las "oraciones" de jQuery en un contexto que asegure que el documento esté completamente cargado

```
$(document).ready(function(){

  // aquí dentro irían todas las "oraciones" de jQuery que necesitemos.

});
```

Si juntamos todo lo recién, tenemos lo siguiente: 

```
<script src="https://ajax.googleapis.com/ajax/libs/jquery/3.3.1/jquery.min.js"></script>
<script>
$(document).ready(function(){
  $("button").click(function(){
    $(".test").hide();
  });
});
</script>
```

Y para cerrar, imaginemos que lo que necesitamos esconder es el primer nombre de los que encontramos en https://api.myjson.com/bins/unf1s

```
<script src="https://ajax.googleapis.com/ajax/libs/jquery/3.3.1/jquery.min.js"></script>
<script>
$(document).ready(function(){
  $.getJSON('https://api.myjson.com/bins/unf1s', function(a) {
    $(".test").append(a[0].name);
    $("button").click(function(){
      $(".test").hide();
    });
  });
});
</script>
```

Obviamente, para que esto funcione, dentro del documento HTML debería tener un elemento con clase `test` y un botón: 

```
<div class="test"></div>
<button>Botón</button>
```

- - - - - - -

#### Referencias:

JSON:

- [{ } myjson - A simple JSON store for your web or mobile app](http://myjson.com/)

- [A collection of small corpuses of interesting data for the creation of bots and similar stuff](https://github.com/dariusk/corpora)

- [crossorigin.me](https://corsproxy.github.io/)

- [JSONLint - The JSON Validator](https://jsonlint.com/)

- [Open Notify - Open APIs From Space](http://open-notify.org/)

- [USGS - GeoJSON Summary Format](https://earthquake.usgs.gov/earthquakes/feed/v1.0/geojson.php)

jQuery:

- [Conceptos básicos de jQuery](https://www.arkaitzgarro.com/jquery/capitulo-3.html#conceptos-basicos-de-jquery)

- [Curso gratis de jQuery](https://codigofacilito.com/cursos/jquery)

- [How jQuery Works](https://learn.jquery.com/about-jquery/how-jquery-works/)

- [Quakit - jQuery Tutorial](https://www.quackit.com/jquery/tutorial/what_is_jquery.cfm)

- [w3schools - jQuery Tutorial](https://www.w3schools.com/jquery/default.asp)


- - - - - - - 

###### [SIGUIENTE CLASE →](https://github.com/profesorfaco/dno037-2019/tree/gh-pages/clase-09)
