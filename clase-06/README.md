# Diseño y Nuevos Medios → Clase 6  

### Miércoles 10 de abril → JS → DOM, variables y JSON

JavaScript (JS en lo que siga) es un lenguaje de programación. Con este lenguaje se pueden escribir programas que serán ejecutados en el navegador que cargue la página web que lo contiene o lo incluye a modo de script `<script>…</script>`. 

En un programa de JS podemos encontrar dos elementos básicos: código y datos. La parte del código es la que permite hacer cosas dentro de la página web. La parte de datos es la que define el estado de la página web en un momento determinado, y los datos de un programa se guardan dentro de variables. Así, por ejemplo, dentro de un documento HTML podemos escribir: 

```
<script>
  var d = new Date();
  var h = d.getHours();
  var saludo;
  if ((h >= 6) && (h < 12)) { 
    saludo = "buenos días"
  } else if ((h >= 12) && (h < 20)) {
    saludo = "buenas tardes"
  } else { 
    saludo = "buenas noches"
  }
  document.write(saludo);
</script>
```

En el ejemplo se crea una variable `d`, a la que se le asigna almacenar la fecha en la que se carga la página web (considerando hasta los segundos). Luego, a una variable `h` se le asigna solo la hora en esa fecha. Después se crea una variable con el nombre `saludo`, y no se le asigna dato para almacenar de forma inmediata. Mediante [condiciones](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Statements/if...else) (`if (…){…}`, `else if (…){…}`, `else{…}`) se le asigna a la variable `saludo` almacenar la cadena de caracteres que corresponda a la hora en que se carga la página web. Finalmente, se escribe el valor de `saludo` en el [Document Object Model o DOM](https://www.w3schools.com/js/js_htmldom.asp) de la página web ya cargada.

#### 1. DOM

[Document Object Model o DOM](https://www.w3schools.com/js/js_htmldom.asp) es


#### 2. Variables

En programación, una variable está formada por un espacio en el sistema de almacenaje (memoria principal del computador) y un identificador asociado a dicho espacio. Este espacio contendrá una cantidad conocida o desconocida de datos, que pueden ir variando en la medida que el programa se ejecuta (y esta es la razón del nombre). 

En lenguajes de programación de propósito general, tales como [C++](https://es.wikipedia.org/wiki/C%2B%2B) o [Java](https://es.wikipedia.org/wiki/Java_(lenguaje_de_programaci%C3%B3n)), o en derivados como [Processing](https://processing.org/), las variables se crean escribiendo el **tipo de dato, espacio, nombre de la variable, asignación, valor y fin de la instrucción con punto y coma**, como en `int a = 3;`, `float b = 3.14`, `String c = "Pi"`.

**Pero en la creación de variables en JS omite la declaración del tipo de dato: Para todo evento [se puede utilizar `var`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Statements#Declarations), lo que implica escribir ***var*, espacio, nombre de la variable, asignación, valor y fin de la instrucción con punto y coma**.

Respecto del **nombre de la variable** habría que indicar tres cosas: (1) no corresponde iniciarlas con números, (2) no se puede usar espacios, tildes ni acentos, y (3) corresponde evitar el uso de [palabras reservadas](https://developer.mozilla.org/es/docs/Web/JavaScript/Referencia/Palabras_Reservadas) por el lenguaje de programación en uso.

Para la **asignación** de un valor se utiliza un signo igual **=**, lo que no debes confundir con un doble signo igual **==**, que es un operador utilizado para comprobar la igualdad, pero jamás para asignar un valor.

Podemos tener una variable a la que se le asigna un valor numeral, entero o decimal `var a = 1;`

Podemos tener una variable a la que se le asigna una cadena de caracteres o *string*, en este caso la cadena de caracteres debe estar contenida por 'comillas simples' o "comillas dobles": `var a = "uno";`

Podemos tener una variable a la que se le asigna un arreglo o *array*:

`var a = ["uno", 2, "tres",4, "cinco"];`

Luego, dentro del arreglo, tenemos distintas posiciones partiendo del cero. Así podemos obtener el valor "uno" cuando pedimos `a[0]`

También podemos tener una variable a la que se le asigna un "object" como contenido:

`var a = {uno:"gato", dos:"perro", tres:"tortuga", cuatro:"iguana"};`

En este caso, podemos pedir los contenidos del objeto *por su nombre*. Podemos obtener el valor "gato" cuando pedimos `a.uno`

Luego podemos comenzar a mezclar:

```
var a = [ { name: "Sergey Prokopyev", craft: "ISS" }, { name: "Alexander Gerst", craft: "ISS" }];
```

En este caso, si quisiera obtener el nombre "Sergey Prokopyek", tendría que ir por `a[0].name`, porque se trata de un arreglo (`[…]`), que contiene objetos (`[{…},{…},{…}]`).

#### 3. JSON

[JSON (JavaScript Object Notation)](https://www.json.org/json-es.html) es un formato de texto sencillo para el intercambio de datos. La última versión de la variaba `a` está basada en un JSON que pueden consultar en http://api.open-notify.org/astros.json

Uno podría tomar un JSON en línea y "[parsearlo](http://www.alegsa.com.ar/Dic/parseo.php)" para que sus datos se conviertan en los datos de una variable en un JS. Esto se podría hacer de la siguiente manera: 

```
var request = new XMLHttpRequest();
request.open('GET', ' https://earthquake.usgs.gov/earthquakes/feed/v1.0/summary/4.5_day.geojson', true);
request.onload = function () {
var a = JSON.parse(this.response);
console.log(a);
}
request.send();	
```

En el caso recién presentado, la variable `a` contendrá un sumario de los últimos movimientos telúricos sobre 4.5 que han sido [registrados en las últimas 24 horas la USGS](https://earthquake.usgs.gov/earthquakes/feed/v1.0/geojson.php).

- - - - - - -

#### Referencias

JavaScript

- [Fundamentos de JavaScript](https://developer.mozilla.org/es/docs/Learn/Getting_started_with_the_web/JavaScript_basics)

- [JavaScript for Beginner](http://xahlee.info/js/js_basics_index.html)

- [JavaScript para Gatos](https://jsparagatos.com/)

- [JavaScript Tutorial](https://www.w3schools.com/js/)

- [JS CheatSheet](https://htmlcheatsheet.com/js/)

- [Programación en JavaScript/Variables](https://es.wikibooks.org/wiki/Programaci%C3%B3n_en_JavaScript/Variables)

JSON

- [JSONLint - The JSON Validator](https://jsonlint.com/)

- [Trabajando con JSON](https://developer.mozilla.org/es/docs/Learn/JavaScript/Objects/JSON)

- - - - - - - 

###### [SIGUIENTE CLASE →](https://github.com/profesorfaco/dno037-2019/tree/gh-pages/clase-07)
