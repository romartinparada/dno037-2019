# Diseño y Nuevos Medios → Clase 2  

### Miércoles 13 de marzo → CSS3

CSS es Cascading Style Sheets, Hojas de Estilo en Cascada. Es un lenguaje utilizado para describir la presentación de documentos HTML. Su bloque constructivo más básico es la regla. Cada regla se inicia con sus [selectores](https://developer.mozilla.org/es/docs/Web/CSS/Referencia_CSS#Selectores), para luego contener, entre paréntesis de llave, determinadas [propiedades](https://www.w3schools.com/cssref/default.asp):

<pre><code>selector{propiedad:valor;}</code></pre>

Con CSS puedo establecer que el elemento `<h1>hola mundo</h1>` se presente con [Helvetica](https://www.w3schools.com/cssref/css_websafe_fonts.asp), [cuerpo de 2 **em**](https://franciscoamk.com/unidades-de-medida-en-css/), y en [rojo](https://en.wikipedia.org/wiki/Web_colors):
```
h1{
font-family: Helvetica, sans-serif; 
font-size: 2em;
color: rgb(255,0,0);
}
```
En este caso, el selector es `h1` y la declaración es todo lo contenido entre paréntesis de llave `{…}`. Como pueden ver, la declaración contiene dentro suyo otros pares (**propiedad** y **valor**), separados unos de otros mediante punto y coma `;`.

¿Cómo es que esta regla, que tiene selector `h1`, le dice a un elemento HTML `<h1>…</h1>`que debe mostrarse de tal manera? 

<p>La respuesta es obvia, "porque h1 es h1". Así mismo, por ejemplo, si en el HTML queremos afectar a <code>&lt;body&gt;todo lo visible dentro de la ventana&lt;body&gt;</code>, en CSS escribimos:</p>

<pre><code><span>body</span>{
  font-family:Helvetica, Arial, sans-serif;
}
</code></pre>

<p>Pero una regla CSS también puede apuntar a <a href="https://developer.mozilla.org/es/docs/Web/CSS/Pseudoelementos" target="_blank">una parte de un elemento HTML (pseudoelemento)</a>. Por ejemplo, si en el HTML queremos afectar a la primera línea de un <code>&lt;p&gt;párrafo&lt;p&gt;</code>, en CSS escribimos:</p>

<pre><code>p<span>::first-line</span>{
  text-transform: uppercase;
}
</code></pre>

<p>Incluso podemos apuntar a <a href="https://developer.mozilla.org/es/docs/Web/CSS/Pseudo-classes" target="_blank">un estado especial del elemento (pseudoclase)</a>. Por ejemplo, si en el HTML queremos afectar a un <code>&lt;a&gt;vínculo&lt;a&gt;</code> mientras el mouse se posa encima, en CSS escribimos:</p>

<pre><code>a<span>:hover</span>{
  text-decoration: underline;
}
</code></pre>

<p>¡Y podemos seguir agregando posibilidades!</p> 

<p>Una regla CSS puede apuntar a cualquier elemento que tenga una clase (class) determinada. Así podemos afectar a un <code>&lt;p <span>class=&quot;alumna&quot;</span>&gt;párrafo&lt;/p&gt;</code>, una <code>&lt;div <span>class=&quot;alumna&quot;</span>&gt;división&lt;/div&gt;</code> o cualquier otro elemento:</p>

<pre><code><span>.</span>alumna{
  border:5px solid rgba(255,255,255,1);
}
</code></pre>

<p>También podemos apuntar a cualquier elemento que tenga una identidad (id) determinada. La diferencia con el caso anterior, es que se recomienda entregarle a un único elemento una identidad:</p>

<pre><code><span>#</span>mariana{
  color:rgba(255,200,200,1);
}
</code></pre>

<p><strong>Ahora bien, para que cada regla CSS afecte al elemento HTML correspondiente, nos falta mencionar algo más: Cómo conectar a un conjunto de reglas CSS con un determinado conjunto de elementos HTML (sea parte de una o varias páginas HTML).</strong></p>

La respuesta es doble, porque hay dos* posibilidades: 

<p>1. Incluyéndolas en la cabeza del documento HTML:</p>

<pre><code>&lt;style&gt;
body{
  color:white;
  background:black;
  font-family:Helvetica, Arial, sans-serif;
  font-size:1em;
}

#mariana{
  color:rgba(255,200,200,1);
}

&lt;/style&gt;
</code></pre>

<p>2. Vinculando un documento CSS independiente, dentro de la cabeza del documento HTML:</p>

<pre><code>&lt;link rel=&quot;stylesheet&quot; href=&quot;estilo.css&quot; type=&quot;text/css&quot;&gt;</code></pre>
 
<p>* Podría reclamarse que estoy olvidando una posibilidad, que es la menos eficiente de todas. La posibilidad en la que puedo meter lenguaje CSS como variable de un atributo en elementos HTML. Para quien reclame, eso se hace como sigue, pero no lo recomiendo:</p>

<pre><code>&lt;p <span>style=&quot;color:red;&quot;</span>&gt;esto es un párrafo&lt;/p&gt;</code></pre>

- - - - - 

#### Referencias:

- [CSS3 Quick Referencia Guide](https://cloud.netlifyusercontent.com/assets/344dbf88-fdf9-42bb-adb4-46f01eedd629/d7fb67af-5180-463d-b58a-bfd4a220d5d0/css3-cheat-sheet.pdf)

- [Guía Breve de CSS](https://www.w3c.es/Divulgacion/GuiasBreves/HojasEstilo)

- [Guía de desarrollo en CSS](https://developer.mozilla.org/es/docs/Web/Guide/CSS)

- [HTML & CSS - W3C](https://www.w3.org/standards/webdesign/htmlcss)

- [Starting with HTML + CSS](https://www.w3.org/Style/Examples/011/firstcss.en.html)
