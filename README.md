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
En este caso, la declaración se mueve a la parte superior al momento de ejecución y no nos generarñia ningún fallo llamarla antes de declararla.

## 5. Diferencia entre la palabra clave var y let
Cuando se declara la variable var podemos acceder a ella de manera global mientras que con let solo podemos acceder en ese bloque de código

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

## 12. Explica las funciones de orden superior en javascript
Una funcion es de orden superior cuando se le pasa como parámetro una funcion o cuando se de devuelve otra funcion

**Se le pasa por parámetro la función:**
```javascript
function primeraFuncion(segundaFuncion()){
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

```

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

## 19. Explique el alcance y la cadena de alcance en javascript
Hay 3 tipos de alcance:
    -Alcance global
    -Alcance local o funcional
    -alcance en bloque

**Alcance global:**
Son las variables o funciones que se pueden acceder a ellas desde cualquier lugar dentro del codigo

```javascript
var variable="Hola mundo";

function aniadeNombre(){
    return varible+" soy Juan";
}
```

**Alcance local o funcional:**
Son las variables que estan declaradas dentro de la funcion, por lo que solo sirven para esa funcion y no se pueden llamar fuera de esta
```javascript
function devuelveNombre(){
    var nombre="Juan"
    return "soy "+nombre;
}
```

**Alcance en bloque:**
Este tipo de alcance esta relacionado con las variables let y const. Las variables con var no tienen alcance en bloque. Las variables con let no se pueden acceder a ellas mientras que con var si
```javascript
{
    let edad=20;
}

console.log(edad) //Nos mostraria un error
```

**Cadena de alcance:**
Son las variables que estan dentro de una funcion, si estas no estan dentro de esa funcion se buscan fuera de la funcion

```javascript
var x = 667;

function function() {

  var otrafuncion = function() {
    console.log(x); // No encuentra x dentro de otraFuncion dentro, asi que la busca fuera
  };
  funcion();
}
```

## 22. ¿Qué son los prototypes de objetos?
    
Todos los objetos de javascript heredan propiedades de un **`prototype`**.

Ejemplos: 
    
> `Date object` heredan propiedades de prototipo fecha
    
> `Math object` heredan propiedades del prototipo matemático
    
> `Array object` heredan propiedades del prototipo Array
    
> Encima de la cadena está `Object.prototype`, cada prototipo hereda propiedades y métodos de `Object.prototype`
    
Esto nos permite usar propiedades y métodos en un objeto incluso si las propiedades y métodos no existen en el objeto actual  
    
    
Ejemplo:
    
```jsx
    const miArray = [];
    miArray.push(2);
    console.log(miArray);
    //[2]
```
    
El motor de javascript ve que el método `push()` no existe en el objeto de Array actual  y, por lo tanto, busca el método push dentro del prototipo Array y encuentra el método.
    
Siempre que la propiedad o método no se encuentre en el objeto actual, el motor de javascript siempre intentará buscar en su prototipo y si aún no existe, buscará dentro del prototipo del prototipo.

## 23. ¿Qué son los callbacks?

A la acción de llamar a una función dentro de otra función (pasada o no pasada por parámetro) se le llama callback

```javascript
elevarADos(num) {
    console.log(Math.pow(num, 2));
}

operacion(num1, num2, operacion) {
    operacion(num1, num2);
}
```
En este ejemplo podemos ver dos ejemplos, una donde simplemente llamamos a un "console.log()" dentro de la función y otro ejemplo donde pasamos como parámetro una función la cual se utilizará dentro.

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

# Preguntas técnicas avanzadas

## 2. ¿Qué se entiende por patrón de diseño de prototipo?
Es el prototipo de un objeto, es como crear un objeto a partir de una plantilla que tienes definida en el objeto (pasándole unos parámetros) y ya podrías creas el objeto con sus valores correspondientes

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

Una promesa tiene 3 estados:
    
- **Pending**: Estado inicial de la promesa.
- **Fulfilled**: Cuando se resuelve/completa la promesa.
- **Rejected**: Cuando se rechaza o no se completa la promesa.
- **Settled**: Cuando la promesa se resuelve o rechaza.

Pare crear una promesa se utiliza su propio constructor

```javascript
function sumarElementosMayor5(num1, num2) {
    return new Promise((resolve,reject) => {
        (num1+num2>5)?resolve('La suma es mayor a 5') : reject('La suma no es mayor a 5')
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

## 16. ¿Es JavaScript un lenguaje de paso por referencia o de paso por valor?
JavaScript para las variables usa un paso por valor, aunque en los objetos se pasa por referencia pero esta sigue siendo pasada por valor, por lo que recibe una copia, estas modificaciones que se hagan a la copia también son afectadas a la original

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
