
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


## Recursos adicionales

* [MDN: Comparison Operators](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/Comparison_Operators)
* [MDN: Control Flow](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Statements/if...else)
* [MDN: Logical Operators](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/Logical_Operators)
* [MDN: for Loops](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Statements/for)
