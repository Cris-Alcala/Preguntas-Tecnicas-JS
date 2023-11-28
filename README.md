# Preguntas técnicas de iniciación

# Preguntas de la entrevista de JavaScript para principiantes

## 1. ¿Cuáles son los diferentes tipos de datos presentes en JavaScript?

### A - Tipos primitivos
**String** : representa una serie de caracteres y se escribe entre comillas. Una cadena se puede representar mediante comillas simples o dobles.

 Ejemplo :

 ~~~jsx
  let str = "Vivek Singh Bisht"; //usando doble comillas
  let str2 = 'John Doe'; //usando comillas simples
 ~~~
 
 - **Número**

Representa un número y se puede escribir con o sin decimales.

Ejemplo :

```jsx
let x = 3; 
let y = 3.6;
```

- **BigInt**

Este tipo de datos se utiliza para almacenar números que están por encima de la limitación del tipo de datos Número. Puede almacenar números enteros grandes y se representa agregando "n" a un literal entero.

Ejemplo :

```jsx
let bigInteger =  234567890123456789012345678901234567890;
```

- **Booleano**

Representa una entidad lógica y sólo puede tener dos valores: verdadero o falso. Los booleanos se utilizan generalmente para pruebas condicionales.

Ejemplo :

```jsx
let a = 2;
let b =  3;
let c =  2;
(a == b) // returns false
(a == c) //returns true
```

- **Indefinido**

Cuando una variable se declara pero no se asigna, tiene el valor indefinido y su tipo también es indefinido.

Ejemplo :

```jsx
let x; // valor de x es indefinido

let y = 'ejemplo';
let y = undefined; // podemos cambiar el valor de una variable a undefined
```

- **Nulo**

Representa un valor inexistente o no válido.

Ejemplo :

```jsx
let z = null;
```

**B. Tipos no primitivos**

- Los tipos de datos primitivos sólo pueden almacenar un único valor. Para almacenar valores múltiples y complejos, se utilizan tipos de datos no primitivos.
- Objeto: se utiliza para almacenar una recopilación de datos.

Ejemplo:

```jsx
// Colección de datos clave-valor
let obj1 = {
   x:  43,
   y:  "Hello world!",
   z:function(){
return this.x;
   }
}

// Colección de datos en una matríz o array
let array1 = [5, "Hello", true, 4.1];
```

## 2. ¿Qué es la elevación en Javascript?

La elevación es un comportamiento de Javascript en el cual al momento de ejecución las declaraciones de las variables, constantes y funciones se mueven a la parte de arriba tanto global como localmente.

```javascript
modifyFunction(); // Llamamos a la función

let modifyFunction = () => {
    // Cuerpo de la función
}
```
En este caso, la declaración se mueve a la parte superior al momento de ejecución y no nos generaría ningún fallo llamarla antes de declararla.

## 3. ¿Por qué usamos la palabra "debugger" en javascript?
El "debugger" del navegador debe estar activado para poder depurar el código. Los "debuggers" integrados se pueden activar y desactivar, lo que requiere que el usuario informe los fallos. Las sección restante del código debería detener la ejecución antes de pasar a la siguiente línea durante la depuración

## 4. Diferencia entre los operadores "==" y "==="
La principal diferencia entre ambos operadores es que == se utiliza para comparar valores, mientras que === se utiliza para comparar tanto valores como tipos.

**Ejemplo**

```Javascript
    let num1 = '3';
    let num2 = 3;

    (num1 == num2)// Devuelve true porque ambos valores son iguales
    (num1 === num2)// Devuelve false porque los tipos son diferentes
```

## 5. Diferencia entre la palabra clave var y let
Cuando se declara la variable var podemos acceder a ella de manera global mientras que con let solo podemos acceder en ese bloque de código

## 6. Explicación de la Coerción
También conocido como conversión automática implicita de valores (Ej: de cadena de texto a número). 
La coerción en JavaScript se refiere a la conversión automática de un tipo de dato a otro durante la ejecución de operaciones. Esto puede ocurrir de manera implícita o explícita. La coerción implícita ocurre automáticamente por el motor de JavaScript, mientras que la coerción explícita es cuando tú como desarrollador realizas la conversión de manera deliberada.
### Coerción Implícita:
**1. Coerción numérica:**
 ~~~jsx
var numero = "123";
var resultado = numero + 5;  // Se produce coerción implícita a número
console.log(resultado);     // Resultado: 128 (123 + 5)
 ~~~
En este caso, JavaScript convierte la cadena "123" a un número para realizar la operación de suma.
**2. Coerción de Cadenas:**
 ~~~jsx
var cadena = 42;
var resultado = "La respuesta es: " + cadena;  // Se produce coerción implícita a cadena
console.log(resultado);                        // Resultado: "La respuesta es: 42"
 ~~~
En este caso, JavaScript convierte la cadena "123" a un número para realizar la operación de suma.
### Coerción Explícita:
**1. Coerción a número:**
 ~~~jsx
var cadena = "123";
var numero = Number(cadena);  // Coerción explícita a número
console.log(numero);          // Resultado: 123
 ~~~
Utilizando la función Number(), se realiza una coerción explícita de la cadena a un número.
**2. Coerción a cadena:**
 ~~~jsx
var numero = 456;
var cadena = String(numero);  // Coerción explícita a cadena
console.log(cadena);          // Resultado: "456"
 ~~~
Mediante la función String(), se realiza una coerción explícita del número a una cadena.

La coerción puede conducir a comportamientos inesperados, por lo que es importante entender cómo funciona y manejarla adecuadamente en tus programas. Además, es una buena práctica realizar conversiones explícitas cuando sea posible para evitar sorpresas en tu código.

## 8. ¿Qué es la propiedad NaN en JavaScript?
    
La propiedad NaN representa el valor "No es un número" . Indica un valor que no es un número legal.
    
 **typeof** de NaN devolverá un **Número** .
    
Para comprobar si un valor es NaN, usamos la función **isNaN()** ,
    
>  La función `isNaN()`  convierte el valor dado a un tipo Número y luego equivale a NaN.

Ejemplo: 
 
```jsx
    isNaN("Hello")  // Returns true
    isNaN(345)   // Returns false
    isNaN('1')  
    // Devuelve falso, ya que '1' se convierte al tipo Número, lo que da como resultado 0 (un número)
    
    isNaN(true) 
    // Devuelve falso, ya que verdadero convertido al tipo Número da como resultado 1 (un número)
    
    isNaN(false) // Returns false
    isNaN(undefined) // Returns true
```

## 9. ¿Paso por valor o paso por referncia?

Cuando hablamos de paso por valor o paso por referencia hablamos de la manera de la que se asigna un valor de una variable a otra cuando se utiliza "=", como por ejemplo:

```javascript
let x = 100;
let y = x;
```

Hay dos comportamientos que se tiene que tener en cuenta, en el caso de los tipos de datos primitivos (string, number, boolean...) y los datos no primitivos (por ejemplo objetos).

En el caso de los datos primitivos como viene a ser el ejemplo anterior los datos de una variable se copian a la otra pero esta segunda variable apunta a otro espacio de memoria. Es decir, si yo modifico "x", en "y" no afecta.

```javascript
x = 200;
console.log(x); // 200
console.log(y); // 100
```

El otro caso es el de los tipo de datos no primitivos en el cual mostraremos un ejemplo:

```javascript
let persona = {nombre:'Eladio'}
let persona_2 = persona;

persona.nombre = 'Cris';

console.log(persona.nombre) // Cris
console.log(persona_2.nombre) // Cris
```

Como podemos ver, el paso es por referencia, esto quiere decir que se pasa la referencia del espacio de memoria y se copia, no los datos en sí.

## 10. ¿Qué es una función invocada inmediatamente en JavaScript?
Es una función que se ejecuta tan pronto como se define.

**Sintaxis de IIFE**
```javascript
(function(){
    console.log("Estoy dentro de un IIFE");
})();
```
Para comprender el IIFE, debemos comprender los dos conjuntos de paréntesis que se agregan al crear un IIFE:

**Primer conjunto de paréntesis:**
```javascript
(function (){
    // Código aqui...
})
```

**Al ejecutar código javascript, cada vez que el compilador ve la palabra "function", asume que estamos declarando una función en el código. Por lo tanto, si no usamos el primer conjunto de paréntesis, el compilador arroja un error porque cree que estamos declarando una función y, según la sintaxis de declarar una función, una función siempre debe tener un nombre.**
```javascript
function (){
    // Código aqui...
}
```

Si queremos eliminar este error ponemos el primer conjunto de paréntesis

**El segundo par de paréntesis**
```javascript
(function (){
    // Código aqui...   
})();
```
En resumen, el IIFE tiene dos propósitos principales:
- Crear variables privadas para evitar conflictos con otros scripts o módulos.
- Proporcionar una forma segura y organizada de encapsular funciones y variables.

## 11. ¿Que es el modo estricto en Javascript y cuáles son sus caracteristicas?

El modo estricto en javascript es una funcion que permite escribir código o una funcion en un entorno operativo "estricto".
En 'Modo Estricto', se lanzarán todas las formas de errores, incluidos los errores silenciosos. Como resultado, la depuración se vuelve mucho más simple. 
Así se reducen las posibilidades del programador de cometer un error.

Caracteristicas:

1.Los argumentos duplicados no son permitidos por los desarrolladores.

2.En modo estricto, no podrás usar la palabra clave JavaScript como parámetro o nombre de función.

3.La palabra clave 'use strict' se utiliza para definir el modo estricto al inicio del script. El modo Estricto es compatible con todos los navegadores.

4.Los ingenieros no podrán crear variables globales en 'Strict Mode'

## 12. Explica las funciones de orden superior en javascript
Una funcion es de orden superior cuando se le pasa como parámetro una funcion o cuando se de devuelve otra funcion

**Se le pasa por parámetro la función:**
```javascript
function primeraFuncion(segundaFuncion){
    segundaFuncion();
}
```

**Devuelve una funcion:**
```javascript
function primeraFuncion() {

  return function() {
    return "Hola mundo";
  }

}

let segundaFuncion = primeraFuncion();
console.log(segundaFuncion()); // Hola Mundo      

```

## 13. Explicación de la palabra reservada `this`
La palabra clave `this` en JavaScript se refiere al objeto al cual hace referencia.
**Ejemplo:**
 ~~~jsx
class EjemploClase {
    constructor(nombre) {
        this.nombre = nombre;
    }

    mostrarNombre() {
        console.log(this.nombre);  // Se refiere a la instancia de la clase creada
    }
}

const instancia = new EjemploClase("Ejemplo");
instancia.mostrarNombre();  // Resultado: "Ejemplo"
 ~~~
 En este ejemplo, `this` dentro del método mostrarNombre se refiere a la instancia de la clase EjemploClase. En este contexto, `this` apunta al objeto específico creado a partir de la clase.

## 14. ¿Qué son las funciones de autoinvocación?
 Una función autoinvocable es una función que se llama automáticamente en el momento de su creación.

 Puede ser anónima:

 ~~~jsx
(function(){
    console.log("Estoy dentro de un IIFE");
})();
 ~~~

 O puede ser nombrada:

 ~~~jsx
(function nombreFuncion(){
    console.log("Estoy dentro de un IIFE");
})();
 ~~~
## 15. Explique los métodos `call()`, `apply()` y `bind()`.
    
- `call()` :
    
Es un método predefinido en javascript que invoca una función o método especificando el objeto propietario.
    
Ejemplo:
    
```jsx
    function saludo(){
    return “Hola” + this.name;
    }
    const objeto = {name:“Sandy”};
    // “Hola Sandy”;
```
    
El método `call()` permite que un objeto utilice el método (función) de otro objeto.
    
Ejemplo:
    
```jsx
    const persona = {
    	edad:23,
    getEdad: function(){
    	return this.edad;
    	}
    }
    const persona2={edad:54};
    persona.getEdad.call(persona2);
    // 54
```
    
Ejemplo 2: `call()` acepta argumentos
    
```jsx
    function decirAlgo(mensaje){
    	return this.nombre + " is " + mensaje;
    }
    
    const persona4 = {nombre:"Jhon"};
    decirAlgo.call(persona4, "awesome");
    // Jhon is awesome
```
    
- `apply()` : 
    
Es similar al método call() , la diferencia es que el método call() toma los argumentos por separado, mientras que apply() toma los argumentos como una matriz.

Ejemplo:
    
```jsx
    function decirAlgo(mensaje){
    	return this.nombre + "is" + mensaje;
    }
    const persona4 ={nombre: "John"};
    decirAlgo.apply(persona4, ["awesome"]);
    //Jhon is awesome
```
    
- `bind()` :
    
Este método devuelve una función, donde el valor de `this`palabra clave, estará vinculado al objeto propietario que se proporciona como parámetro.
    
Ejemplo:
    
```jsx
    const  bicicletaInfo{
    	detalles: function(numRegistro, nombreMarca){
    		return this.nombreCliente, "detalles de la bici: " + numRegistro + ", "+ nombreMarca;
    	}
    }
    
    const cliente1 = {nombreCliente:"Fran"};
    const detallesCliene1 = bicicletaInfo.detalles.bind(cliente1, "TS0122", "Bullet");
    // enlaza la funcion detalles con cliente1
    
    detallesCliente1();
    //Fran, detalles de la bici: TS0122, Bullet
```

## 16. Diferencias entre test() y exec() en RegExp

Estas funciones son propias de las expresiones regulares (RegExp) con las que podremos comprobar de maneras diferentes si una cadena pasa o no una comprobación de una expresión regular.

### Método "test()"

Este método devuelve "true" o "false" dependiendo si la cadena la cual se comprueba pasa o no la comprobación de la expresión regular.

```javascript
let regExp = /n/;
regExp.test('no'); // true
```

### Método "exec()"

Este método te devuelve un arreglo con diferentes elementos (cadena buscada, indice de la primera referencia, cadena comprobada y un campo llamado nombre) si pasa la prueba o "null" si no encuentra ninguna referencia. 

```javascript
let regExp = /n/;
regExp.exec('no'); // [ 'n', index: 0, input: 'no', groups: undefined ]
```
## 17. ¿Qué es el currying en JavaScript?
La técnica del currying es una forma de programación funcional en la cual se aplica la función de manera recursiva.

```javascript
function sumar(a) {
  return function(b){
    return a + b;
  }
}

sumar(3)(4) 
```

Si tenemos una función es que sumar(a,b), la función después del curry sería sumar(a)(b), en este caso no se cambia la funcionalidad de la función, solo la forma en llamar a la función.

```javascript
function multiply(a,b){
  return a*b;
}

function currying(fn){
  return function(a){
    return function(b){
      return fn(a,b);
    }
  }
}

var curriedMultiply = currying(multiply);

multiply(4, 3); // Returns 12

curriedMultiply(4)(3); // Also returns 12
```
**Se ha transformado la función multiplicar(a,b) en una función curryMultiply en la que toma un parámetro a la vez**
## 18.Javascript externo: Principales Ventajas

Un código javascript externo es un codigo javascript escrito en un archivo separado
con la extension js que se puede vincular bien en un elemento "head" o en un elemento "body" del archivo html donde se desee implementar el código.

Algunas ventajas de javascript externo son

1.Permite a los diseñadores y desarrolladores de la web colaborar en archivos HTML y javascript.
2.Podemos reutilizar el código.
3.La legibilidad de código es simple en javascript externo.


## 19. Explique el "scope" y la "scope chain" en javascript
Hay 3 tipos de alcance:
    - Global scope
    - Local or function scope
    - Block scope

**Global scope:**
Son las variables o funciones que se pueden acceder a ellas desde cualquier lugar dentro del codigo

```javascript
var variable="Hola mundo";

function aniadeNombre(){
    return varible+" soy Juan";
}
```

**Local or function scope:**
Son las variables que estan declaradas dentro de la funcion, por lo que solo sirven para esa funcion y no se pueden llamar fuera de esta
```javascript
function devuelveNombre(){
    var nombre="Juan"
    return "soy "+nombre;
}
```

**Block scope:**
Este tipo de alcance esta relacionado con las variables let y const. Las variables con var no tienen alcance en bloque. Las variables con let no se pueden acceder a ellas mientras que con var si
```javascript
{
    let edad=20;
}

console.log(edad) //Nos mostraria un error
```

**Scope chain:**
Son las variables que estan dentro de una funcion, si estas no estan dentro de esa funcion se buscan fuera de la funcion

```javascript
var x = 667;

function funcion() {

  var otraFuncion = function() {
    console.log(x); // No encuentra x dentro de otraFuncion, asi que la busca fuera, en el siguiente scope (funcion). Tampoco la encuentra y ya la busca en el scope global. Ahí sí la encuentra y por tanto muestra 667
  };
  otraFuncion();
}

funcion();
```

## 20. Closures en JavaScript.
Un "closure" en JavaScript es una característica que permite a una función interna acceder y recordar las variables de su función externa, incluso después de que la función externa haya terminado de ejecutarse. Esto se logra cuando una función interna es definida dentro de otra función (función externa) y es utilizada fuera de esa función externa.

Los closures son útiles para crear estructuras de datos complejas y funciones más flexibles al preservar el estado de las variables. 
**Ejemplo:**
 ~~~jsx
const add = (function () {
  let counter = 0;
  return function () {
       counter += 1; 
       return counter
  }
})();

add(); // counter es 1
add(); // counter es 2
add(); // counter es 3
 ~~~
A la variable add se le asigna lo que devuelve la función autoinvocable.
La función autoinvocable sólo se ejecuta una vez, establece el valor de counter a 0 y devuelve una función que modifica dicha variable. Esa es la función que asigna a add.
Por tanto, add es una closure o clausura, esto es, una función con acceso a una variable privada como es counter.
La variable counter está protegida por el scope de la función anónima y sólo puede ser cambiado utilizando la función add.
Este es el principio del hook useState que se verá en React. Por lo que es muy importante entender su funcionamiento.

## 21. Menciona algunas ventajas de javascript.

JavaScript es un lenguaje versátil que funciona en el cliente y el servidor. Para el backend, Node.js es la opción principal. Es fácil de aprender y potencia funciones avanzadas en páginas web. Además, es rápido para los usuarios finales, mejorando la experiencia en aplicaciones web.

## 22. ¿Qué son los prototypes de objetos?
    
Todos los objetos de javascript heredan propiedades de un **`prototype`**.

Ejemplos: 
    
> `Date object` heredan propiedades de prototipo Date
    
> `Math object` heredan propiedades del prototipo Math
    
> `Array object` heredan propiedades del prototipo Array
    
> Encima de la cadena está `Object.prototype`, cada prototipo hereda propiedades y métodos de `Object.prototype`
    
Esto nos permite usar propiedades y métodos en un objeto incluso si las propiedades y métodos no existen en el objeto actual  
    
    
Ejemplo:
    
```jsx
let arr = [2,3,4];

arr.push(5); // [2,3,4,5]

arr.__proto__.push = (val) => console.log("push hackeado para que no añada " + val);

arr.push(6); // push hackeado para que no añada 6  
arr.push(7); // push hackeado para que no añada 7 
```
    
El motor de javascript ve que el método `push()` no existe en el objeto de Array actual  y, por lo tanto, busca el método push dentro del prototipo Array y encuentra el método.
    
Siempre que la propiedad o método no se encuentre en el objeto actual, el motor de javascript siempre intentará buscar en su prototipo y si aún no existe, buscará dentro del prototipo del prototipo.

## 23. ¿Qué son los callbacks?

A la acción de llamar a una función dentro de otra función (pasada o no pasada por parámetro) se le llama callback

```javascript
elevar(num, exponente) {
    console.log(Math.pow(num, exponente));
}

operacion(num1, num2, elevar) {
    elevar(num1, num2);
}
```
En este ejemplo podemos ver dos ejemplos, una donde simplemente llamamos a un "console.log()" dentro de la función y otro ejemplo donde pasamos como parámetro una función la cual se utilizará dentro.

## 24 - ¿Cuáles son los tipos de errores en javascript?
Existen 2 tipos de errores.

- **Error de sintaxis:** Los errores de sintaxis son errores o problemas ortográficos en el ódigo que hacen que el programa no se ejecute en absoluto o deje de ejecutarse a mitad de camino.
- **Error lógico:** Los errores de razonamiento ocurren cuando la sintaxis es adecuada para la lógica o el programa es incorrecto

## 25.¿Qué es la memorización?

La memorización (en inglés memoization) es el modo por el cual el valor de retorno de una funcion se guarda en la caché en función de sus parámetros.

Si no se cambia el parámetro de esa función, se devuelve la versión en caché de la función.

**Ejemplo**

``` Javascript 

    function memoizedMultiplyTo3(){
        let cache = [];

        return function(num){
            if(num in cache){
                console.log("valor almacenado en caché");
                return cache[num];
            }else{
                cache[num] = num * 3;
                return cache[num];
            }
        }
    }

    let memoizedFunc = memoizedMultiplyTo3(); // accedemos desde memoizedFunc a la variable privada cache de la función externa memoizedMultiplyTo3().

    memoizedFunc(20); // devuelve el valor normal
    memoizedFunc(20);// devuelve el valor guardado en caché
```

### Explicacion:
En el código anterior, si ejecutamos la función memoizedFunc con el mismo parámetro, en lugar de calcular el resultado de nuevo, devuelve el resultado en caché.


## 26. ¿Qué es la recursividad en un lenguaje de programación?
Es hacer que una funcion se llame así misma hasta obtener el resultado correcto
```javascript 
let numero=0;
function llegarADiez(){
    if(numero<10){
        numero++;
        llegarADiez();
    }
}
```

## 27. Uso de un constructor en JavaScript.
Los constructores son funciones usadas para crear objetos en JavaScript.

Si queremos crear múltiples objetos en JavaScript con propiedades y métodos similares, las funciones constructor son usadas.
 ~~~jsx
// Definición del constructor
function Persona(nombre, edad) {
  // Propiedades de la persona
  this.nombre = nombre;
  this.edad = edad;

  // Método para obtener información de la persona
  this.obtenerInformacion = function() {
    return `Nombre: ${this.nombre}, Edad: ${this.edad}`;
  };
}

// Creación de instancias utilizando el constructor
var persona1 = new Persona("Juan", 25);
var persona2 = new Persona("María", 30);

// Uso de métodos y propiedades
console.log(persona1.obtenerInformacion());  // Resultado: "Nombre: Juan, Edad: 25"
console.log(persona2.obtenerInformacion());  // Resultado: "Nombre: María, Edad: 30"
 ~~~

## 29.  ¿Qué método se utiliza para recuperar un carácter de un índice determinado?
    
La función `charAt()` de `string` de JavaScript encuentra un elemento char en el índice proporcionado.

 El número de índice comienza en 0 y continúa hasta n-1. Aquí n es la longitud de la cadena. 

El valor del índice debe ser positivo, mayor o igual que la longitud de la cadena.

## 30. ¿Qué es el BOM?

Es el modelo de objetos del explorador.

Nos permite interactuar con el navegador, como por ejemplo la ventana del navegador, el BOM no permitirá acceder a sus atributos como el historial, pantalla, navegador, ubicación...

Aquí dejaré un ejemplo de como se abriría una ventana nueva con el BOM.

```javascript
let nuevaVentana = window.open("", "nuevaVentana", "width=800,height=600");
```
## 31 - ¿Cuál es la distinción entre JavaScript del lado del cliente y del lado del servidor?
- JavaScript del lado del cliente se compone de dos partes, un lenguaje fundamental y objetos predefinidos para ejecutar JavaScript en un navegador. JavaScript para el cliente se incluye automáticamente en las páginas HTML. En tiempo de ejecución, el navegador comprende este script.
- JavaScript del lado del servidor implica la ejecución de código JavaScript en un servidor en respuesta a las solicitudes del cliente. Maneja estas solicitudes y entrega la respuesta relevante al cliente, que puede incluir JavaScript del lado del cliente para su posterior ejecución dentro del navegador.

# Preguntas técnicas avanzadas

## 1.¿Cuáles son las funciones flecha?

Las funciones de flecha se introdujeron en la versión ES6 de javascript. Nos proporcionan una nueva y más corta sintaxis para declarar funciones. Las funciones de flecha sólo se pueden utilizar como expresión de función.

**Funcion normal**

```javascript
    
    function resta(num1,num2){
        return num1 - num2;
    }

```

**Funcion Flecha**

```javascript
    
    let resta = (num1,num2) => num1 + num2;

```

### Explicación

Las funciones de flecha se declaran sin la palabra clave de la función. Si sólo hay una expresión que devuelve, entonces no necesitamos usar la palabra clave de retorno, así como en una función de flecha como se muestra en el ejemplo anterior.

```javascript
    
    let sumar5 = num1 => num1 + 5;

```

Si la función toma sólo un argumento, entonces el paréntesis () alrededor del parámetro se puede omitir como se muestra en el código anterior.

## 2. ¿Qué se entiende por patrón de diseño de prototipo?
Es el prototipo de un objeto, es como crear un objeto a partir de una plantilla que tienes definida en el objeto (pasándole unos parámetros) y ya podrías creas el objeto con sus valores correspondientes

## 3. Diferencias al declarar variables usando var, let y const.
En JavaScript, hay tres maneras de declarar variables: var, let y const. Cada una tiene sus propias características y comportamientos.

| Palabra clave        | const | let | var |
|----------------------|-------|-----|-----|
| Ámbito Global        | No    | No  | Sí  |
| Ámbito de Función    | Sí    | Sí  | Sí  |
| Ámbito de Bloque     | Sí    | Sí  | No  |
| Puede Ser Reasignada | No    | Sí  | Sí  |

### `var`
**Ámbito de función:**
Las variables declaradas con var tienen un ámbito de función. Esto significa que están disponibles en toda la función en la que se declaran, incluso antes de la línea de declaración.

**Reasignación y redeclaración:**
Se pueden reasignar y redeclarar dentro de su ámbito.

**Hoisting:**
Las declaraciones var se izan (hoisted) al principio de su ámbito, pero solo la declaración, no la inicialización.
 ~~~jsx
function ejemploVar() {
  if (true) {
    var x = 10;
  }

  console.log(x);  // Resultado: 10 (var tiene ámbito de función)
}
 ~~~

### `let`
**Ámbito de bloque:**
Las variables declaradas con let tienen un ámbito de bloque. Esto significa que están limitadas al bloque en el que se declaran.

**No permite redeclaración:**
No puedes redeclarar la misma variable en el mismo ámbito.

 ~~~jsx
function ejemploLet() {
  if (true) {
    let y = 20;
    console.log(y);  // Resultado: 20 (let tiene ámbito de bloque)
  }

  // console.log(y);  // Esto generaría un error, ya que y no está definido aquí
}
 ~~~

### `const`
**Ámbito de bloque:**
Al igual que let, const tiene un ámbito de bloque.

**Asignación única y no redeclaración:**
La variable debe asignarse al momento de la declaración y no puede ser reasignada. Además, no se permite la redeclaración en el mismo ámbito.

 ~~~jsx
function ejemploConst() {
  const z = 30;
  // z = 40;  // Esto generaría un error, ya que no se puede reasignar una constante
  // const z = 40;  // Esto también generaría un error, ya que no se puede redeclarar en el mismo ámbito

  console.log(z);  // Resultado: 30
}
 ~~~

## 5. En JavaScript, ¿con cuántos métodos diferentes puedes crear un objeto?
    
- Con Object
    
    Ejemplo:
    
    ```jsx
    // Crear un objeto utilizando el constructor Object
    const persona = new Object();
    
    persona.nombre = "Juan";
    persona.edad = 30;
    
    persona.saludar = function() {
      console.log("Hola, soy " + this.nombre + " y tengo " + this.edad + " años.");
    };
    
    persona.saludar();
    ```
    
- Usando Class
    
    Ejemplo:
    
    ```jsx
    // Crear un objeto utilizando la declaración de clase (ES6+)
    class PersonaClase {
      constructor(nombre, edad) {
        this.nombre = nombre;
        this.edad = edad;
      }
    
      saludar() {
        console.log("Hola, soy " + this.nombre + " y tengo " + this.edad + " años.");
      }
    }
    
    const personaConClase = new PersonaClase("Carlos", 40);
    personaConClase.saludar();
    ```
    
- Método create()
    
    Ejemplo:
    
    ```jsx
    // Crear un objeto utilizando Object.create()
    const prototipoPersona = {
      saludar: function() {
        console.log("Hola, soy " + this.nombre + " y tengo " + this.edad + " años.");
      }
    };
    
    const personaConCreate = Object.create(prototipoPersona);
    personaConCreate.nombre = "Ana";
    personaConCreate.edad = 28;
    personaConCreate.saludar();
    ```
    
- con Object Literals
    
    Ejemplo:
    
    ```jsx
    // Crear un objeto utilizando Object Literals
    const persona = {
      nombre: "Juan",
      edad: 30,
      saludar: function() {
        console.log("Hola, soy " + this.nombre + " y tengo " + this.edad + " años.");
      }
    };
    
    persona.saludar();
    ```
    
- Usando function()
    
    Ejemplo:
    
    ```jsx
    // Crear un objeto utilizando una función
    function crearPersona(nombre, edad) {
      const persona = {};
      persona.nombre = nombre;
      persona.edad = edad;
      persona.saludar = function() {
        console.log("Hola, soy " + this.nombre + " y tengo " + this.edad + " años.");
      };
      return persona;
    }
    
    const nuevaPersona = crearPersona("Maria", 25);
    nuevaPersona.saludar();
    ```
    
- Usando el Objeto constructor
    
    Ejemplo:
    
    ```jsx
    // Crear un objeto utilizando un objeto constructor
    function Persona(nombre, edad) {
      this.nombre = nombre;
      this.edad = edad;
      this.saludar = function() {
        console.log("Hola, soy " + this.nombre + " y tengo " + this.edad + " años.");
      };
    }
    
    const otraPersona = new Persona("Pedro", 35);
    otraPersona.saludar();
    ```
    

## 6. ¿Qué son las promesas?

Las promesas se utilizan para manejar operaciones asíncronas, es decir, que pueden tardar tiempo en resolverse como por ejemplo una petición a un servidor.

Una promesa tiene 4 estados:
    
- **Pending**: Estado inicial de la promesa.
- **Fulfilled**: Cuando se resuelve/completa la promesa.
- **Rejected**: Cuando se rechaza o no se completa la promesa.
- **Settled**: Cuando la promesa se resuelve o rechaza.

Para crear una promesa se utiliza su propio constructor

```javascript
function sumarElementosMayor5(num1, num2) {
    return new Promise((resolve,reject) => {
        (num1+num2>5)?resolve('La suma es mayor a 5') : reject('La suma no es mayor a 5');
    });
}    
```

En el ejemplo anterior cuando llamamos a la función devuelve una promesa que se resuelve o se rechaza dependiendo de si la suma de los elementos es menos o mayor a 5.

Al momento de consumir la promesa se hace de la siguiente manera.

- **.then()**: Se utiliza para consumir la promesa y trabajar con los resultados cuando se resuelve.
- **.catch()**: Se utiliza para acceder al resultado cuando la promesa ha sido rechazada.

Para consumir la promesa anterior se podría hacer de la siguiente manera:

```javascript
sumarElementosMayor5(4,5)
    .then(response => console.log(response)) // Muestra la el mensaje del "resolve"
    .catch(error => console.log(error)) // Muestra el mensaje del "reject" en el caso de que no se resuelva
```
## 7 - ¿Qué son las clases en JavaScript?
Las clases en JavaScript son una de las características más avanzadas y versátiles de la plataforma. Las clases son una construcción de alto nivel que permite a los desarrolladores crear objetos con características similares y con un comportamiento predecible.

Un ejemplo de clase en JavaScript sería:
```javascript
class Auto {
 constructor(marca, modelo, color) {
    this.marca = marca;
    this.modelo = modelo;
    this.color = color;
 }

 mostrarInformacion() {
    console.log(`Marca: ${this.marca}, Modelo: ${this.modelo}, Color: ${this.color}`);
 }
}
```

**Para utilizar esta clase, podemos crear instancias de la misma de la siguiente manera:**
```javascript
let auto1 = new Auto('Toyota', 'Corolla', 'Rojo');
let auto2 = new Auto('Honda', 'Civic', 'Blanco');

auto1.mostrarInformacion(); // Marca: Toyota, Modelo: Corolla, Color: Rojo
auto2.mostrarInformacion(); // Marca: Honda, Modelo: Civic, Color: Blanco
```

## 8.¿Qué son las funciones generadoras?

Las funciones generadoras son una clase especial de funciones que se pueden detener a mitad de camino y luego continuar desde donde se habían detenido.

**En las funciones normales, utilizamos la palabra clave de retorno para devolver un valor y tan pronto como se ejecute la declaración de retorno, la ejecución de la función se detiene:**

```javascript
    function mostrarValor(valor){
        return valor;
        console.log(15) // Esta línea no se ejecutará
    }
```

**En el caso de las funciones generadoras, cuando se les llama, no ejecutan el código, en cambio, devuelven un objeto generador. Este objeto generador se encarga de la ejecución.**

```javascript
    function *holaMundo(){
        yield 'holaMundo';
        yield 'soy dani';
    };

    holaMundo(); // devuelve un objeto de tipo generador
```

## 9. Explique WeakSet en javascript
Es un array de objetos únicos y ordenados. Solo permite objetos.Tiene que cumplir 3 puntos:
-Solo contienen objetos
-Si el objeto no tiene nada creado es recogido como basura (No sirve)
-Solo tiene 3 métodos, add(), delete() y has()

```javascript
let objeto1={
    nombre:"Juan",
    apellido:"Lara",
    edad:20
}
let objeto2={
    nombre:"Juan",
    apellido:"Lara",
    edad:20
}
const nuevoSet =new WeakSet([objeto1])
nuevoSet.add(objeto2);
```

## 10. ¿Por que usamos callbacks?
Un callback en JavaScript es una función que se pasa como argumento a otra función y que se ejecuta después de que se completa alguna operación específica.

Se utiliza principalmente para manejar operaciones asíncronas, controlar el flujo de ejecución y gestionar eventos en el desarrollo de aplicaciones, ya que JavaScript es un lenguaje basado en eventos. Es decir, en vez de esperar una respuesta antes de continuar, JavaScript continuará su ejecución mientras monitoriza eventos adicionales.

Los callbacks son una técnica de asegurarte que un código en particular no se ejecuta hasta que otro código haya completado su ejecución.

## 12.  ¿Qué es la desestructuración de objetos?
    
La desestructuración de objetos es una nueva forma de extraer elementos de un objeto o un array
    
Ejemplo antes de la versión ES6, sin desestructuración:
    
```jsx
    const usuario = {
      nombre: "Juan",
      edad: 30,
      ciudad: "Buenos Aires"
    };
    
    //Extración manual de las propiedades
    const nombre = usuario.nombre;
    const edad = usuario.edad;
    const ciudad = usuario.ciudad;
    
    console.log(nombre); //Juan
    console.log(edad); //30
    console.log(ciudades); //Buenos Aires
```
    
Ejemplo de desestructuración:
    
```jsx
    const usuario = {
      nombre: "Juan",
      edad: 30,
      ciudad: "Buenos Aires"
    };
    
    //Desestructuración de objetos
    const {nombre, edad, ciudad } = usuario;
    
    // Uso de las variables desestructuradas
    console.log(nombre);  // Juan
    console.log(edad);    // 30
    console.log(ciudad);  // Buenos Aires
```
    
La desestructuración no solo es útil para objetos, sino que también se puede aplicar a matrices o arrays. Proporciona una forma más clara y concisa de trabajar con datos estructurados en JavaScript.

## 13. Diferencia entre herencia prototípica y clásica

En la herencia prototípica, los objetos heredan directamente propiedades y métodos de otros objetos. Cada objeto tiene una propiedad privada (referida como su "Prototype") que mantiene un enlace a otro objeto llamado su prototipo. Un ejemplo de herencia prototípica es:

```javascript
let animal = {
  come: function() {
    console.log("El animal está comiendo");
  }
};

let perro = Object.create(animal);

perro.ladra = function() {
  console.log("El perro está ladrando");
};

perro.come(); // El animal está comiendo
perro.ladra(); // El perro está ladrando
```

En la herencia clásica, las clases heredan propiedades y métodos de otras clases. Aunque JavaScript no tiene clases en el sentido tradicional, la palabra clave class permite una sintaxis que se parece mucho a la herencia clásica. Un ejemplo de herencia clásica es:

```javascript
class Animal {
  constructor(nombre) {
    this.nombre = nombre;
  }

  come() {
    console.log(this.nombre + " está comiendo");
  }
}

class Perro extends Animal {
  ladra() {
    console.log(this.nombre + " está ladrando");
  }
}

let miPerro = new Perro("Rex");
miPerro.come(); // Rex está comiendo
miPerro.ladra(); // Rex está ladrando
```
## 14. ¿Qué es una zona muerta temporal?
La zona muerta temporal es un comportamiento que ocurre con variables declaradas usando palabras clave let y const . Es un comportamiento en el que intentamos acceder a una variable antes de que se declare. Ejemplos de zona muerta temporal:
```javascript
x = 23; // Gives reference error

let x;

function anotherRandomFunc(){
  message = "Hello"; // Throws a reference error

  let message;
}
anotherRandomFunc();
```

## 15.¿Qué son los patrones de diseño en Javascript?

Los patrones de diseño son formas de estructuar el código en javascript cuya finalidad es crear código más estable.

Se dividen principalmente en 3 categorías:

**Patrón de Diseño de Creación:**El mecanismo de generación de objetos es abordado por el Patrón de Diseño Creacióntivo JavaScript. Su objetivo es hacer los artículos que sean apropiados para un determinado escenario.

**Patrón de Diseño Estructural:** El Patrón de Diseño Estructural JavaScript explica cómo las clases y objetos que hemos generado hasta ahora se pueden combinar para construir marcos más grandes. Este patrón hace que sea más fácil crear relaciones entre ítems definiendo una forma directa de hacerlo.

**Patrón de Diseño de Comportamiento:** Este patrón de diseño resalta patrones típicos de comunicación entre objetos en JavaScript. Como resultado, la comunicación puede llevarse a cabo con mayor libertad.

## 16. ¿Es JavaScript un lenguaje de paso por referencia o de paso por valor?
JavaScript para las variables usa un paso por valor, aunque en los objetos se pasa por referencia pero esta sigue siendo pasada por valor, por lo que recibe una copia, estas modificaciones que se hagan a la copia también son afectadas a la original

## 17. Diferencia entre el uso de Async/Await y Generators para lograr la misma funcionalidad.

- Las funciones generadoras se ejecutan paso a paso, lo que significa una salida a la vez, mientras que las funciones Async/await se ejecutan secuencialmente una después de otra.

- Async/await facilita ciertos casos de uso de las funciones generadoras para ejecutarse de manera más sencilla.

- El resultado de salida de la función generadora siempre es value: X, done: Boolean, pero el valor de retorno de la función Async es siempre una promesa o genera un error.

## 19.  ¿Cuál es el papel de los scripts diferidos en JavaScript?
    
Los scripts diferidos en JavaScript son scripts que no se ejecutan tan pronto como se cargan en la página web, sino que **se retrasan hasta que la página ha terminado de analizarse y construirse**.

El uso del atributo `defer` en la etiqueta `<script>` se utiliza para lograr este comportamiento. El papel principal de los scripts diferidos es mejorar el rendimiento de la carga de la página web.

 Aquí hay algunos puntos clave sobre el papel de los scripts diferidos:
    
1. **Retraso de la ejecución**: Los scripts diferidos no bloquean el análisis y renderizado de la página. Se descargan en segundo plano mientras el resto de la página se analiza y se construye.


2. **Ejecución en orden**: Aunque los scripts se descargan en paralelo, se ejecutan en el orden en el que aparecen en el documento HTML. Esto significa que el primer script diferido en el HTML se ejecutará antes que el segundo, y así sucesivamente.

3. **Mejora del rendimiento de carga**: Al retrasar la ejecución de scripts, se puede mejorar la percepción del tiempo de carga para los usuarios, ya que la página principal se carga y se muestra más rápidamente. Esto es especialmente útil en páginas con muchos scripts o contenido extenso.
    
Ejemplo:
    
```html
    <!DOCTYPE html>
    <html lang="es">
    <head>
        <meta charset="UTF-8">
        <meta name="viewport" content="width=device-width, initial-scale=1.0">
        <title>Mi Página</title>
        <!-- Otros elementos del encabezado -->
        <script defer src="script1.js"></script>
        <script defer src="script2.js"></script>
    </head>
    <body>
        <!-- Contenido de la página -->
    </body>
    </html>
```

## 20. ¿Qué hay que hacer para poner en práctica el Alcance Léxico?

- **Define una función**: Esta será tu función externa.
- **Declara variables en la función externa**: Estas variables estarán disponibles para cualquier función interna.
- **Define una función interna dentro de la función externa**: Esta función interna tendrá acceso a las variables de la función externa gracias al alcance léxico.
- **Usa las variables de la función externa dentro de la función interna**: Puedes referenciar directamente las variables de la función externa, como si fueran variables locales en la función interna.

```javascript
function funcionExterna() {
  var variableExterna = "¡Hola, mundo!";
  
  function funcionInterna() {
    console.log(variableExterna); // Accede a la variable de la función externa
  }
  
  funcionInterna();
}

funcionExterna(); // Imprime: ¡Hola, mundo!
```
## 21 - ¿Cuál es el propósito del siguiente código JavaScript?
```javascript
var scope = "global scope";
function check() 
{
    var scope = "local scope"; 
    function f() 
    { 
         return scope; 
    }
    return f;
}
```
Cada función de ejecución, bloque de código y script en su conjunto en JavaScript tiene un objeto relacionado conocido como entorno léxico. La línea de código anterior devuelve el valor dentro del alcance.
