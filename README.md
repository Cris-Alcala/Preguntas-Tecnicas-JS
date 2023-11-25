# Preguntas técnicas de iniciación

## 2. ¿Qué es la elevación en Javascript?

La elevación es un comportamiento de Javascript en el cual al momento de ejecución las declaraciones de las variables, constantes y funciones se mueven a la parte de arriba tanto global como localmente.

```javascript
modifyFunction(); // Llamamos a la función

let modifyFunction = () => {
    // Cuerpo de la función
}
```
En este caso, la declaración se mueve a la parte superior al momento de ejecución y no nos generarñia ningún fallo llamarla antes de declararla.

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

## 30. ¿Qué es el BOM?

Es el modelo de objetos del explorador.

Nos permite interactuar con el navegador, como por ejemplo la ventana del navegador, el BOM no permitirá acceder a sus atributos como el historial, pantalla, navegador, ubicación...

Aquí dejaré un ejemplo de como se abriría una ventana nueva con el BOM.

```javascript
let nuevaVentana = window.open("", "nuevaVentana", "width=800,height=600");
```

# Preguntas técnicas avanzadas

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
