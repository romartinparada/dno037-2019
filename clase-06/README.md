# Diseño y Nuevos Medios → Clase 6  

### Miércoles 10 de abril → JS → DOM, variables y JSON

JavaScript es un lenguaje de programación. 

`console.log(Math.round(Math.PI))`

En este ejemplo pueden aprovechar lo aprendido en álgebra y aritmética: los paréntesis indican que las operaciones que ellos encierran tienen prioridad ante las demás. O sea, lo primero es explicar que `Math.PI` entrega el número π, número que se redondea (`Math.round`) para luego imprimirlo en la [consola de JavaScript de navegador](https://norfipc.com/inf/como-usar-consola-javascript-navegador-web.php) (`console.log`). 

Porque programar es escribir, en cierto lenguaje, un conjunto ordenado y finito de operaciones que permiten hacer algo. Por ejemplo: 

```
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
```

En el ejemplo se crea una variable `d`, a la que se le asigna almacenar el dato de la fecha en la que se carga la página web (considerando hasta los segundos). Luego, a una variable `h` se le asigna solo la hora en esa fecha. Después se crea una variable con el nombre `saludo`, y no se le asigna dato para almacenar de forma inmediata.

Mediante [condiciones](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Statements/if...else) (`if (…){…}`, `else if (…){…}`, `else{…}`) se le asigna a la variable `saludo` almacenar la cadena de caracteres que corresponda a la hora en que se carga la página web. 

Finalmente, se escribe el valor de `saludo` en el [Document Object Model o DOM](https://www.w3schools.com/js/js_htmldom.asp) de la página web ya cargada.

#### 1. DOM

[Document Object Model o DOM](https://www.w3schools.com/js/js_htmldom.asp) es

#### 2. Variables

En programación, una variable está formada por un espacio en el sistema de almacenaje (memoria principal del computador) y un identificador asociado a dicho espacio. Este espacio contendrá una cantidad conocida o desconocida de datos, que pueden ir variando en la medida que el programa se ejecuta (y esta es la razón del nombre). 

En lenguajes de programación de propósito general, tales como [C++](https://es.wikipedia.org/wiki/C%2B%2B) o [Java](https://es.wikipedia.org/wiki/Java_(lenguaje_de_programaci%C3%B3n)), o en derivados como [Processing](https://processing.org/), las variables se crean escribiendo el **tipo de dato, espacio, nombre de la variable, asignación, valor y fin de la instrucción**, como en `int a = 29;`

Para entender esto por partes, vamos primero con algunos **tipos de dato**: 

tipo | es | ocupa 
--- | --- | --- 
`boolean` | [*true or false*](https://processing.org/reference/boolean.html) | 1 byte
`int` | [entero](https://processing.org/reference/int.html) | 4 bytes 
`float` | [decimal simple](https://processing.org/reference/float.html) | 4 bytes
`String` | [cadena de carácteres](https://processing.org/reference/String.html) | variable

Respecto del **nombre de la variable** habría que indicar tres cosas: (1) no corresponde iniciarlas con números,   (2) no se puede usar espacios, tildes ni acentos, y (3) corresponde evitar el uso de [palabras reservadas](https://developer.mozilla.org/es/docs/Web/JavaScript/Referencia/Palabras_Reservadas) por el lenguaje de programación en uso.

Para la **asignación** de un valor se utiliza un signo igual **=**, lo que no debes confundir con un doble signo igual **==**, que es un operador utilizado para comprobar la igualdad, pero jamás para asignar un valor.

Y para el finalizar, se agrega un punto y coma.

**La creación de variables de JS simplifica el primer paso**, el de la declaración del tipo de variable: Para todo tipo se utiliza `var`, lo que deja el asunto en **var, espacio, nombre de la variable, asignación, valor y fin de la instrucción**. Pero igualmente corresponde poner atención al tipo de dato asignado, porque:

Podemos tener una variable a la que se le asigna un número, entero o decimal `var a = 1;`

Podemos tener una variable a la que se le asigna una cadena de caracteres o *string*, en este caso la cadena de caracteres debe estar contenida por 'comillas simples' o "comillas dobles": `var a = "uno";`

Podemos tener una variable a la que se le asigna un arreglo o *array*:

`var a = ["uno", "dos", "tres","cuatro",5];`

Luego, dentro del arreglo, tenemos distintas posiciones partiendo del cero:

```
a[0] = "uno"
a[1] = "dos"
a[2] = "tres"
a[3] = "cuatro"
a[4] = 5
```
También podemos tener una variable a la que se le asigna un "object" como contenido:

`var a = {uno:"gato", dos:"perro", tres:"tortuga", cuatro:"iguana"}`

Y podemos pedir los contenidos del objeto *por su nombre*:

```
a.uno = "gato"
a.dos = "perro"
a.tres = "tortuga"
a.cuatro = "iguana"
```

Y podemos comenzar a mezclar:

```
var a = [
 {
  name: "Sergey Prokopyev",
  craft: "ISS"
 },
 {
  name: "Alexander Gerst",
  craft: "ISS"
 }
]
```

En este caso, si quisiera obtener el nombre "Sergey Prokopyek", tendría que ir por `a[0].name`, porque se trata de un arreglo (`[…]`), que contiene objetos (`[{…},{…},{…}]`).

#### 3. JSON

[JSON (JavaScript Object Notation)](https://www.json.org/json-es.html) es un formato de texto sencillo para el intercambio de datos. La última versión de la variaba `a` está basada en un JSON que pueden consultar en http://api.open-notify.org/astros.json

Uno podría tomar un JSON en línea y "[parsearlo](http://www.alegsa.com.ar/Dic/parseo.php)" para que sus datos se conviertan en los datos de una variable en un JavaScript. Esto se podría hacer de la siguiente manera: 

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

- [Fundamentos de JavaScript](https://developer.mozilla.org/es/docs/Learn/Getting_started_with_the_web/JavaScript_basics)

- [Introducción a Javascript: Tipos de variables](https://librosweb.es/libro/javascript/capitulo-3/tipos-de-variables.html)

- [JavaScript for Beginner](http://xahlee.info/js/js_basics_index.html)

- [JavaScript para Gatos](https://jsparagatos.com/)

- [JavaScript Tutorial](https://www.w3schools.com/js/)

- [JS CheatSheet](https://htmlcheatsheet.com/js/)

- [JSONLint - The JSON Validator](https://jsonlint.com/)

- [Statements and declarations - JavaScript | MDN](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Statements#Declarations)

- [Programación en JavaScript/Variables](https://es.wikibooks.org/wiki/Programaci%C3%B3n_en_JavaScript/Variables)

- [Trabajando con JSON](https://developer.mozilla.org/es/docs/Learn/JavaScript/Objects/JSON)

- - - - - - - 

###### [SIGUIENTE CLASE →](https://github.com/profesorfaco/dno037-2019/tree/gh-pages/clase-07)
