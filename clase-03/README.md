# Diseño y Nuevos Medios → Clase 3  

### Miércoles 20 de marzo → HTML5

HTML es Lenguaje de Marcado para Hipertextos (HyperText Markup Language), un lenguaje utilizado para escribir . [HTML5](https://developer.mozilla.org/es/docs/HTML/HTML5) es la versión más reciente de este lenguaje. 

Su bloque constructivo más básico es el elemento. Cada elemento de HTML se escribe, generalmente, entre etiquetas:

```
<etiqueta>contenido</etiqueta>
```

Así, cada elementos HTML es un "sandwich", con las etiquetas como rebanadas de pan, y el contido como relleno. Con estos "sadwiches" definimos qué se ve en una página web. Por ejemplo:

```
<p>esto es un párrafo</p>
```

Aunque también hay elementos HTML que nos obligan a cambiar la analogía del sandwich por canapé:

```
<etiqueta>
```

Ejemplos de estos elementos como "canapé", son:

```
<meta>, <hr>, <br>, <img> 
```

Si extendemos la analogía, podemos decir que cada elemento, puede estar determinado por uno o varios atributos incluídos en su primera o única rebanada de pan; y cada atributo tiene su variable.

Como canapé:

```
<etiqueta atributo="variable">
```

Como sandwich:

```
<etiqueta atributo="variable">contenido</etiqueta>
```

Deben notar que atributos y variables se escriben en la primera etiqueta, la de apertura, nunca en la de cierre.

Mediante atributos y variables pueden cambiar un simple párrafo a uno que tenga las características de una clase "alumna" y la identidad de "mariana".

```
<p class="estudiante" id="francisca">esto es un párrafo</p>
```

Estas variables, estudiante y francisca, por sí mismas no significan nada, en otro lugar habría que entregarles un significado.

Atributos y variables también nos permiten establecer vínculos y recursos. Así, por ejemplo, puedo establecer un recurso de imagen que se llama "selfie", que tiene extensión "jpg", e indicar que un clic en ella me "lleve" a Google:

```
<a href="http://www.google.cl"><img src="selfie.jpg"></a>
```

- - - - - - 

#### Referencias:

[Introducción a HTML](https://developer.mozilla.org/es/docs/Learn/HTML/Introduccion_a_HTML)

[HTML Tutorial | w3schools.com](https://www.w3schools.com/html/default.asp)

[Element Index | HTML5 Doctor](http://html5doctor.com/element-index/)

[HTML5 Cheat Sheet](https://websitesetup.org/HTML5-cheat-sheet.pdf)

- - - - - - - 

###### [SIGUIENTE CLASE →](https://github.com/profesorfaco/dno037-2019/tree/gh-pages/clase-04)

