
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

# Lección 3: Javascript III

En esta lección cubriremos:

* Operadores lógicos
* Bucles `for` y `while`


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

## Bucles `while`

Al igual que el bucle `for` el `while` es una manera de iterar, pero en esta declaramos una sentencia que va a ejecutar nuestro código mientras que sea verdadera. 

```
let n = 0;

while (n < 3) {
  n++;
}

console.log(n);
// expected output: 3
```

En este caso, le estamos indicando que mientras que `n` sea menor a 3, itere aumentando su valor en uno. Cuando `n` pasa a ser 3 va a dejar de iterar ya que la condición `n < 3` va a ser `false`.


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



## Recursos adicionales

* [MDN: Comparison Operators](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/Comparison_Operators)
* [MDN: Control Flow](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Statements/if...else)
* [MDN: Logical Operators](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/Logical_Operators)
* [MDN: for Loops](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Statements/for)
