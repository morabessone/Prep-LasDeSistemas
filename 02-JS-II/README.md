
<table width="100%" style='table-layout:fixed;'>
  <tr>
    <td>
      <a href="https://airtable.com/shrSzEYT4idEFGB8d?prefill_clase=03-JS-II">
        <img src="https://static.thenounproject.com/png/204643-200.png" width="100"/>
        <br>
        Hacé click acá para dejar tu feedback sobre esta clase.
      </a>
    </td>
  </tr>
</table>

# Lección 2: Javascript II 

En esta lección cubriremos:

* Introducción a las Funciones
* Operadores de comparación
* `arguments`


## Introducción a las Funciones

Las funciones son una parte muy importante de todo lenguaje de programacion y sobre todo en JavaScript. Son tipos particulares de Objetos, llamados `callable objects` u objetos invocables, por lo que tienen las mismas propiedades que cualquier objeto.

Ahora que tenemos un conjunto de variables, necesitamos funciones para calcularlas, cambiarlas, hacer algo con ellas. Hay tres formas en que podemos construir una función.

```javascript
    function miFuncion() {}
    var otraFuncion = function () {};
    var yOtra = () => {};
```

Usaremos la primera forma en esta lección y hablaremos sobre las otras formas en próximas lecciones.

### Anatomía de una Función

```javascript
function miFuncion() {}
```

Una función comenzará con la palabra clave `function`, esto le dice a lo que sea que esté ejecutando tu programa que lo que sigue es una función y que debe tratarse como tal. Después de eso viene el nombre de la función, nos gusta dar nombres de funciones que describan lo que hacen. Luego viene un paréntesis abierto y uno cerrado. Y finalmente, abra y cierre los corchetes. Entre estos corchetes es donde irá todo nuestro código a ejecutar.

```javascript
function logHola() {
    console.log('hola!');
}

logHola();
```

En este ejemplo declaramos una función `logHola` y la configuramos en` console.log` `'hello'`. Entonces podemos ver que para ejecutar esta función, necesitamos escribir el nombre y los paréntesis. Esta es la sintaxis para ejecutar una función. Una función siempre necesita paréntesis para ejecutarse.

### Argumentos

Ahora que podemos ejecutar una función básica, vamos a comenzar a pasarle argumentos.

```javascript
function logHola(nombre) {
    console.log('Hola, ' + nombre);
}

logHola('Martin');
```

Si agregamos una variable a los paréntesis cuando declaramos la función, podemos usar esta variable dentro de nuestra función. Iniciamos el valor de esta variable pasándola a la función cuando la llamamos. Entonces en este caso `nombre = 'Martin'`. También podemos pasar otras variables a esto:

```javascript
function logHola(nombre) {
    console.log( `Hola, ${nombre}`);
}

var miNombre = 'Antonio';
logHola(miNombre);
```

Podemos agregar múltiples argumentos colocando una coma entre ellos:

```javascript
function sumarDosNumeros(a, b) {
  var suma = a + b;
  return suma;
}

sumarDosNumeros(1, 5); // 6
```
### Declaración "return"

En el ejemplo anterior presentamos la declaración `return`. No vamos a usar `console.log` con todo lo que salga de una función. Lo más probable es que queramos devolver algo. En este caso es la suma de los dos números. Piense en la declaración de retorno ("return") como la única forma en que los datos escapan de una función. No se puede acceder a nada más que a lo que se devuelve fuera de la función. También tenga en cuenta que cuando una función llega a una declaración de retorno, la función detiene inmediatamente lo que está haciendo y "devuelve" lo especificado.

```javascript
function dividirDosNumeros(a, b) {
  var producto = a / b;
  return producto;
}

También podemos establecer variables para igualar lo que devuelve una función.

```javascript
function restarDosNumeros(a, b) {
  var diferencia = a - b;
  return diferencia;
}
```

## Operadores de comparación

En este ejemplo, vamos a utilizar operadores de comparación. El flujo de control ("control flow") es una forma de que nuestra función verifique si algo es `true`, y ya sea ejecutando el código suministrado si es así o avanzando si no lo es. Para esto usaremos la palabra clave `if`:

```javascript
function puedeManejar(edad) {
    if (edad > 18) {
        return true;
    }

    return false;
}

puedeManejar(22); // true
```

Aquí estamos tomando un número (`edad`) y verificando si la declaración es` true` (`22>18`), lo es, por lo que devolveremos` true`, y la función se detendrá. Si no es así, omitirá ese código y la función devolverá `false`.

El símbolo "mayor que" (`>`) que ve en el último ejemplo se llama _Operador de comparación_. Los operadores de comparación evalúan dos elementos y devuelven `verdadero` o` falso`. Estos operadores son: `<`, `<=`, `>`, `>=`, `===`, `!==`.


```javascript
1 > 2;     // false
2 < 3;     // true
10 >= 10;  // true
100 <= 1;  // false
```

El "triple igual" (`===`) no debe confundirse con un solo signo igual (que indica asignar un valor a una variable). El triple igual comparará todo sobre los dos elementos, incluido el tipo, y devolverá si son exactamente iguales o no:

(Algo a tener en cuenta: hay un "doble igual" (`==`) que comparará dos elementos, pero NO tendrá en cuenta sus tipos (`1 == '1' // verdadero`). Debido a esto , se considera una mala práctica usar el doble igual. Nos gustaría verte siempre usando el triple, y siempre nos verás usándolo.)

```javascript
1 === 1;          // true
1 === '1';        // false
'perro' === 'perro';  // true
'perro' === 'Perro';  // false
```

El último operador de comparación que nos gustaría presentarle tiene dos partes.

Primero es el "NOT" (`!`). Cuando veas esto significará que estamos preguntando lo contrario de la expresión (volveremos a visitar el operador NOT más adelante en esta lección).

Con eso en mente, podemos introducir el "no es igual" (`!==`). Esto devolverá verdadero si los artículos NO son iguales entre sí de alguna manera. Esto, como el triple igual, tiene en cuenta el tipo de dato.

```javascript
1 !== 1;          // false
1 !== '1';        // true
'perro' !== 'perro';  // false
'perro' !== 'Perro';  // true
```
Podemos usar `if` para verificar y ver si una expresión es` true`, si es así, ejecute algún código, o si no es así, que omita el código y siga ejecutando el programa.

```javascript
if (1 + 1 === 2) {
    console.log('La expresión es verdadera');
}
```

Para complementar a `if`, también podemos usar las declaraciones` else if` y `else`. Estas declaraciones deben usarse con `if` y deben venir después de él. Estas declaraciones serán evaluadas si el inicial `if` devuelve `false`. Podemos pensar en el `else if` como otra declaración` if` que se ha encadenado (podemos tener tantas otras declaraciones `if` que queramos). Solo se ejecutará un bloque de código de instrucción `if` o `else if`. Si en algún momento una declaración devuelve `true`, ese código se ejecutará y el resto se omitirá:

```javascript
if (false) {
    console.log('Este código será omitido');
} else if (true) {
    console.log('Este código correrá');
} else if (true) {
    console.log('Este código NO correrá');
}
```
La declaración `else` siempre aparecerá al final de una cadena `if-else` o `if`, y actuará de manera predeterminada. Si ninguna de las expresiones devuelve `true`, el bloque de código `else` se ejecutará sin importar qué. Si alguna de las expresiones anteriores `if` o `else if` son `true`, el bloque de código de instrucción` else` no se ejecutará.

```javascript
if (false) {
    console.log('Este código será omitido');
} else if (false) {
    console.log('Este código NO correrá');
} else {
    console.log('Este código correrá');
}
```
HASTA ACA Clase 2 ------------------------------------------------------------------------------------------------------------------------------------------------

## Operadores lógicos

También podemos combinar dos expresiones de igualdad y preguntar si alguna de las dos es verdadera, si ambas son verdaderas o si ninguna de ellas es verdadera. Para hacer esto, utilizaremos operadores lógicos.

### &&

El primer operador lógico que veremos es el operador "Y" ("AND"). Está escrito con dos símbolos (`&&`). Esto evaluará ambas expresiones y devolverá verdadero si AMBAS expresiones son `true`. Si uno (o ambos) de ellos es falso, este operador devolverá `false`:

```javascript
if (100 > 10 && 10 === 10) {
    console.log('Ambas declaraciones son ciertas, este código se ejecutará');
}

if (10 === 9 && 10 > 9) {
    console.log('Una de las declaraciones es false, por lo que && devolverá false, y este código no se ejecutará');
}
```

### ||

El siguiente es el operador "Ó" ("OR"). Está escrito con dos barras verticales (`||`). Determinará si una de las expresiones es `true`. Devolverá `true` si una (o ambas) de las expresiones es` true`. Devolverá `false` si AMBAS expresiones son` false`:

```javascript
if (100 > 10 || 10 === 10) {
    console.log('Ambas declaraciones son ciertas, este código se ejecutará');
}

if (10 === 9 || 10 > 9) {
    console.log('Una de las declaraciones es true, por lo que || devolverá true y este código se ejecutará');
}

if (10 === 9 || 1 > 9) {
    console.log('Ambas declaraciones son falsas, por lo que || devolverá false y este código no se ejecutará');
}
```

### !

El último operador lógico es el operador "NOT" ("NO"). Está escrito como un solo signo de exclamación (`!`). Vimos este operador antes al determinar la igualdad (`!==`). Como antes, el operador NOT devolverá el valor booleano opuesto de lo que se le pasa:

```javascript
if (!false) {
    console.log('El ! devolverá true, porque es lo contrario de false, así que este código se ejecutará');
}

if (!(1 === 1)) {
    console.log('1 es igual a 1, de modo que la expresión devuelve true. El operador ! devolverá lo contrario de eso, por lo que este código NO se ejecutará');
}
```

### Notas sobre operadores lógicos

Un par de cosas a tener en cuenta sobre los operadores lógicos.

* Las expresiones se evalúan en orden, y la computadora omitirá cualquier expresión redundante. En una declaración `&&`, si la primera expresión es `false`, la segunda expresión no se evaluará porque AMBAS expresiones deben ser` true`. Lo mismo para la declaración `||`. Si la primera expresión es `verdadero`, la segunda no se evaluará porque solo debe haber una declaración` verdadero` para cumplir con los requisitos del operador.

* Usá paréntesis. Como vimos en el segundo ejemplo de operador `!`, usamos paréntesis para evaluar PRIMERO lo que estaba dentro de los paréntesis, luego aplicamos el operador `!`. Podemos ajustar cualquier expresión entre paréntesis y se evaluará antes de evaluar la expresión como un todo.

## Bucles `for`

La mayoría del software se ejecuta en bucles, evaluando expresiones una y otra vez hasta que devuelve lo que estamos buscando o se detiene después de cierto tiempo. Javascript tiene dos expresiones de bucle incorporadas y hoy veremos la primera, el bucle "for".

Los bucles `for` tienen una sintaxis única, similar a la instrucción` if`, pero un poco más compleja. Primero tenemos la palabra clave `for`, seguida de paréntesis y luego abrir y cerrar llaves. Dentro de los paréntesis necesitaremos tres cosas. Primero, debemos declarar una variable, esto es sobre lo que se repetirá el bucle. Entonces tendremos una expresión condicional, el ciclo continuará sucediendo hasta que esta declaración sea `false`. Tercero, incrementaremos nuestra variable. Las tres declaraciones están separadas por un punto y coma.

```javascript
for (let i = 0                 ; i < 10                 ; i++          ) {
// | Declaramos una variable | Expresión condicional | Incrementamos la variable |
    console.log(i);
}
```

En este ejemplo, vemos que inicialmente establecemos nuestra variable `i` en 0, el ciclo se ejecutará y cada vez que llegue al final, aumentará el contador en uno. El bucle `for` evaluará la expresión condicional. Si es `true`, se ejecutará nuevamente, si es `false` dejará de funcionar.

### El operador ++

Vimos en el último ejemplo el operador `++`. Esta es la abreviatura de Javascript para "Establecer el valor de la variable a su valor actual más uno". Hay algunas más de estas expresiones abreviadas de matemática / asignación variable, las visitaremos en las próximas lecciones.

### Bucles infinitos

Es posible que un bucle se atasque en lo que llamamos un "bucle infinito". Debes asegurarte de que haya una forma de finalizar el bucle. Ejemplo de un bucle infinito:

```javascript
for (let i = 0; i >= 0; i++) {
    console.log(i);
}
```

Debido a que nuestra expresión condicional SIEMPRE será `true` (` i` nunca será menor que 0), este ciclo se ejecutará esencialmente para siempre. Esto interrumpirá su programa y puede bloquear su navegador web o computadora.

## Arguments

Como vimos anteriormente, las funciones son objetos invocables, y podemos hacerlo pasándoles argumentos que varíen el comportamiento de estas.

``` javascript
> function log(str) {
    console.log(str)
  }

> log('hola!')
< 'hola!'
```

Si sabemos las variables a tomar, como en el ejemplo `str`, podemos darle nombre a este parámetro. Sino hay una propiedad _**arguments**_ , propia de todas las funciones, que contiene los parámetros pasados como argumento.

``` javascript
> function args() {
    console.log(arguments)
  }

> args('hola!', 'otro parametro', 3)
< ["hola!", "otro parametro", 3, callee: 'function', Symbol(Symbol.iterator): 'function']
```

_arguments_ nos da acceso a la **n** cantidad como parámetros, pero tengamos en cuenta que **no es un Arreglo**.

``` javascript
> function args() {
    return Array.isArray(arguments)
  }

> args(1,2,3)
< false
```

Si queremos saber cuantos parámetros puede recibir una función podemos usar la propiedad `length`.

``` javascript
> args.length
< 0 // porque en la función `args` definimos 0 parámetros
```

## Abre la carpeta "homework" y completa la tarea descrita en el archivo README
[Homework](https://github.com/atralice/Curso.Prep.Henry/tree/master/03-JS-II/homework)

## Recursos adicionales

* [MDN: Comparison Operators](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/Comparison_Operators)
* [MDN: Control Flow](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Statements/if...else)
* [MDN: Logical Operators](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/Logical_Operators)
* [MDN: for Loops](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Statements/for)
