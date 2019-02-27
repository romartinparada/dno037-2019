# Diseño y Nuevos Medios → Clase 7  

### Miércoles 17 de abril → jQuery y JSON

#### jQuery

jQuery es una [biblioteca](https://es.wikipedia.org/wiki/Biblioteca_(informática)) de JS que simplifica la manipulación del DOM, el manejo de eventos, el desarrollo de animaciones y el uso de AJAX (Asynchronous JavaScript And XML; una tecnología que permite a una página web actualizarse de forma dinámica sin que tenga que cargarse completamente).

jQuery se puede incluir o vincular a una página web entre etiquetas `<script></script>`. Y funcionará si y solo si ya ha sido vinculada la biblioteca correspondiente: 

```
<script src="https://ajax.googleapis.com/ajax/libs/jquery/3.3.1/jquery.min.js"></script>
<script>
  //Aquí puedes usar JS simplificado por jQuery
</script>
```

Luego, para utilizar esta biblioteca hay que recordar que, en una oración, el sujeto es quien realiza la acción o de quien se dice algo. Mientras que el predicado describe la acción que realiza el sujeto o lo que se dice del sujeto. Habiendo recordado eso, será fácil comprender qué puede resultar de esto: 

```$("sujeto").predicado();```

Así, por ejemplo, puedo escribir `$(".test").hide()` para indicar que quiero esconder (*hide*) a todos los elementos con clase `test`. ¿Pero bajo qué condiciones quiero esconderlos? Esa condición aún no la defino, y podría hacerlo de la siguiente manera:
 
```
$("button").click(function(){
  $(".test").hide(1000);
});
```

Allí tenemos dos "oraciones". La primera tiene como sujeto a cualquier botón (*button*) y la segunda tiene como sujeto a cualquier elemento de clase *test*. El predicado de la primera es "hacer click" (*click*), mientras el predicado de la segunda es "esconder" (*hide*). Si nos fijamos en los paréntesis `({` y `})`, podemos notar que la segunda oración depende de la primera, con lo que se realizará la acción de la segunda sí y sólo sí se realiza la acción de la primera.

A propósito de paréntesis, una recomendación: Escribir las "oraciones" de jQuery en un contexto que asegure que el documento esté completamente cargado

```
$(document).ready(function(){

  // aquí dentro irían todas las "oraciones" de jQuery que necesitemos.

});
```

Si juntamos todo lo expuesto, tenemos lo siguiente: 

```
<script src="https://ajax.googleapis.com/ajax/libs/jquery/3.3.1/jquery.min.js"></script>
<script>
$(document).ready(function(){
  $("button").click(function(){
    $(".test").hide(1000);
  });
});
</script>
```

#### JSON

[JSON (JavaScript Object Notation)](https://www.json.org/json-es.html) es un formato de texto sencillo para el intercambio de datos. Uno puede tomar un JSON en línea y "parsearlo" para que sus datos se conviertan en los datos de una variable en un JS. Esto se podría hacer de la siguiente manera:

```
var request = new XMLHttpRequest();
request.open('GET', ' https://earthquake.usgs.gov/earthquakes/feed/v1.0/summary/4.5_day.geojson', true);
request.onload = function () {
  var a = JSON.parse(this.response);
  console.log(a);
}
request.send();	
```

En el caso recién presentado, la variable a contendrá un sumario de los últimos movimientos telúricos sobre 4.5 que han sido registrados en las últimas 24 horas la USGS. Pero se puede escribir menos si utilizamos jQuery en lugar de JS a secas: 

```
$.getJSON( 'https://earthquake.usgs.gov/earthquakes/feed/v1.0/summary/4.5_day.geojson', function( data ) {
  console.log(data);
}
```

La única diferencia con el caso anterior: Los datos no quedan en la variable `a`, sino en `data`.

- - - - - - -

#### Referencias:

- [Conceptos básicos de jQuery](https://www.arkaitzgarro.com/jquery/capitulo-3.html#conceptos-basicos-de-jquery)

- [Curso gratis de jQuery](https://codigofacilito.com/cursos/jquery)

- [How jQuery Works](https://learn.jquery.com/about-jquery/how-jquery-works/)

- [jQuery CheatSheet](https://htmlcheatsheet.com/jquery/)

- [Quakit - jQuery Tutorial](https://www.quackit.com/jquery/tutorial/what_is_jquery.cfm)

- [w3schools - jQuery Tutorial](https://www.w3schools.com/jquery/default.asp)

- - - - - - - 

###### [SIGUIENTE CLASE →](https://github.com/profesorfaco/dno037-2019/tree/gh-pages/clase-08)
