# Diseño y Nuevos Medios → Clase 10 

### Miércoles 15 de mayo → PHP → Servidor, variables y ciclos

Personal Home Page o HTML Pre Process.

#### 1. Servidor

Servidor es software 

Relación cliente-servidor

MAMP

#### 2. Variables

Recordemos que, en programación, una variable está formada por un espacio en el sistema de almacenaje (memoria principal del computador) y un identificador asociado a dicho espacio. Este espacio contendrá una cantidad conocida o desconocida de datos, que pueden ir variando en la medida que el programa se ejecuta (y esta es la razón del nombre).

Así como en JavaScript, en PHP tampoco es necesario indicar el tipo de variable con un prefijo especial. A todo tipo de variable le antecede de un símbolo monetario `$`, para luego poner la asignación, valor y fin de la instrucción.  

Una variable a la que se le asigna un único número como contenido:

`$a = 1;`

Una variable a la que se le asigna un "string" como contenido:

`$a = "uno";`

Una variable a la que se le asigna un "array" como contenido:

`$a = array("uno", "dos", "tres","cuatro");`

Por ahora, no revisaremos los objetos en PHP. Pero vamos a profundizar en los "arrays" y "arrays dentro de arrays dentro de arrays…"

Profundicemos con un ejemplo:

`$inception = array("el sueño en la van",array("el sueño en el hotel",array("el sueño en la nieve",array("el sueño en la ciudad abandonada"))))`

La información legible en `$inception` es:
```
Array
(
    [0] => el sueño en la van
    [1] => Array
        (
            [0] => el sueño en el hotel
            [1] => Array
                (
                    [0] => el sueño en la nieve
                    [1] => Array
                        (
                            [0] => el sueño en la ciudad abandonada
                        )

                )

        )

)
```
Si queremos que nos entregue, por ejemplo, el sueño más profundo (el sueño en la ciudad abandonada), tenemos que ir a por `$inception[1][1][1][0]`.

Modifiquemos el ejemplo. Podemos escribir el arreglo de inception de otra manera:

`$inception = array("primero"=>"el sueño en la van","segundo"=>"el sueño en el hotel","tercero"=>"el sueño en la nieve","cuarto"=>"el sueño en la ciudad abandonada")`

Ahora la información legible dentro de la variable es:

```
Array
(
    [primero] => el sueño en la van
    [segundo] => el sueño en el hotel
    [tercero] => el sueño en la nieve
    [cuarto] => el sueño en la ciudad abandonada
)
```

En esta caso, si queremos que nos entregue el sueño más profundo (el sueño en la ciudad abandonada), le tenemos que solicitar un `$inception["cuarto"]`.

#### 3. Ciclos

`<?php for(){} ;?>`

- - - - - - - 

###### [SIGUIENTE CLASE →](https://github.com/profesorfaco/dno037-2019/tree/gh-pages/clase-11)
