
Manual simple javascript es6
==================================

# variables

### declaraciones de bloque

El bloque que consiste en dos llaves el cual nos permite manejar el ámbito de mejor forma
``` javascript
{
let uno = 1; 
// todo lo que se instancia en este bloque
// solo será accesible en el bloque
}

```

### Declaración let

Funciona por medio de un bloque (simplemente una separación por medio de llaves o cualquier expresión que los use) ya que estos crean el ámbito en el cual se va a utilizar y solo existe en ese bloque.
Cuando no podemos alcanzar una variable del tipo var aparece como indefinida cuando no podemos alcanzar una variable tipo let aparece un un error de referencia.
``` javascript
var varibaleGlobal = 5;
{
let variableDeBloque = 3;
}

```

### const

Su sintaxis es muy parecida las constantes en c++ (bueno solo tiene la misma palabra reservada)
Las constantes son variables que su valor no cambia, en si no tiene restricción en el valor si no la asignación, por ejemplo en objetos o vectores usted puede cambiarle valores internos pero no el tipo con el que fue declarado.

### operador propagacion (spread/rest)

ahora e6 produce un operador llamado propagación, este operador consiste en tres punto seguidos antes de la variable que se quiera utilizar,
este consiste dependiendo de donde se va ha utilizar en separar o agrupar valores, ya sea separar los valores de un vector o de forma inversa, agrupar parámetros ingresados en una función y convertirlos en un vector.

``` javascript

function sumaLoQueSeEnvie(...parametros){
let temp = 0;
console.log(parametros);
parametros.forEach((e) => {
temp += e;
});
return temp;
}
sumaLoQueSeEnvie(1,2,3,4);
// 10

```

### variables destructuradas

El destructurado funciona separando valores de un vector o un objeto siendo posible guardarlos variables separadas ahorrándonos escribir varias líneas de código,
suena similar al operador de tres puntos pero funcionan diferente, su sintaxis se utiliza al momento de la declaración de una o varias variables,
si queremos destructurar un objeto envolvemos nuestras variables con llaves {} y queremos destructurar un array las envolvemos
entre corchetes []
``` javascript

var evas = {
eva00:'rei',
eva01:'shinji',
eva02:'asuka'
};

var {eva00,eva01,eva02} = evas;

console.log(eva00);

var pilotos = ['rei','shinji','asuka'];

var [eva00,eva01,eva02] = pilotos;

console.log(eva00);

```

si se desea dejar saltar un valor se deja una coma como representación de ese valor que no se va ha tomar,
también se puede combinar con objetos mucho más elaborados esto se conoce como destructuración anidada combinando las dos formas de destructurar e incluso con el operador de propagación,
en casos especiales si un valor esperado no es retornado por el objeto podemos dejarle un valor por defecto
y por ultimo también podemos utilizar la restructuración cuando estamos definiendo parámetros de funciones e incluso darle valores por defecto. 

``` javascript

function cuenta({carne,pollo=3}){
return carne+pollo;
}

var empanadas = {
carne: 10,
pollo:5
};

cuenta(empanadas);
```

# funciones

### funciones de dirección o flecha =>

Las funciones de flecha tiene una sintaxis mucho mas simple y no se comportan de la misma forma que una función normal
ya que no tiene un constructor no es posible utilizarla como una clase e instanciar la con el operador *new*, si utilizamos esto lanzara un error al momento de ejecutar nuestro código.
es exclusivamente una función anónima, no tiene un valor *this* propio y no es compatible con *arguments* ( la solución a este problema es utilizar el operador de propagación).

Su sintaxis

si se utiliza con solo un parámetro no son necesarios los paréntesis de lo contrario son obligatorios,
las llaves y la palabra clave *return* son opcionales, solo se utilizan si se tiene mas de una expresión,
si solo tenemos una y queremos retornar un objeto literal lo envolveremos entre paracentesis de lo contrario habrá un conflicto
con las llaves de la función.

``` javascript
// una expresión y un parámetro
let saludo = nombre => 'mi nombre es ' + nombre + ' y tiene ' + nombre.length + ' letras' 

saludo('paul')
```

### funciones de nivel de bloque

las funciones de nivel de bloque se utilizan de forma estricta aunque no es obligatorio, 
su comportamiento cambia si no se utilizan de esta forma, siempre que no este igualada a una variable
vienen siendo similares a las funciones auto ejecutables (alcance de la variable)
``` javascript
{
function efimero(){
}
}
```
### valores de parámetros por defecto

ahora en las funciones se pueden asignar valores por defecto a los parámetros, así cuando falta un parámetro
queda por defecto con el valor dado

``` javascript

function a(b = 3, d =5){
return a + d;
}

a(); // 8

```

estos parametros se pueden igualar a otros parametros de la misma funcion, a otras variables y a operaciones e incluso a 
funciones autoejecutables.

# plantillas

es una forma mas clara de concatenar cadenas de caracteres acercándose al formato de cadenas de otros lenguaces como c++, java o php
permite el uso de cadenas en diferentes lineas de código sin utilizar el operador de suma e incluso podemos realizar expresiones dentro de ellas

``` javascript
let pantilla = `{$}`;
```
falta
### preprocesador
falta

### plantillas en crudo 
falta

# objetos

### objetos literales

en ocasiones cuando queremos crear objetos literales utilizamos variables con el mismo nombre
de la propiedad del objeto esto se llama duplicidad, en e6 se a eliminado y se puede crear
de forma directa solo separando el nombre de la propiedad con comas, ya que en e6 cuando
una propiedad de un objeto literal no tiene valor el motor de e6 busca en el bloque
una variable con el mismo nombre y le asigna el valor
``` javascript
var a = 2,b = 3;
var obj = {
a, b;
}
```

también las funciones en objetos literales no es necesario utilizar la palabra reservada *function*

#### setter/getter

son un par de funciones para obtener y retornar un valor que funcionan con las palabras reservadas *set* and *get*
pero no son llamadas como una función si no como una propiedad más

### propiedad con nombre computarizada

son las propiedades las cuales su nombre esta creado por medio de un cadenas, siendo posible sumar uno o más de
cadenas 

``` javascript
var color = {
['eva01']:'morado'
};

console.log(color.eva01);
```
### nombre de propiedades

ahora se puede utilizar la palabra reservada *name* para para obtener una cadena con el nombre de una método,
en algunos casos retorna el tipo de método u el nombre de la función padre, por ejemplo en las enlazadas retorna que
esta ligada y el nombre de la función y el caso de las funciones anónimas retorna anónimo

#### object.assing

llega a remplazar los mixins de muchos frameworks.

### metodos consistentes

en objetos literales y clases no hay necesidad de utilizar la palabra reservada *function*, solo se declara los paréntesis
para los parámetros y las llaves para el cuerpo de la función, esto hace más fácil leer código muy extenso el único problema es
que esta función no puede hacer recursividad. 

### super
es una forma de obtener el comportamiento del prototypo que nos esta heredando ya sea una clase o un metodo
falta

# expresiones regulares

### unicode
falta

# simbolos

es un nuevo tipo primitivo 
o es una función pero no se puede utilizar con el operador *new*
falta

#iteradores 

### for of
es un nuevo ciclo el cual trae las ventajas de un for y un forEach 
falta

#### iterables
son un tipo de símbolo el cual sirve itera (repetir una acción una y otra vez)

#### iteradores
son vectores los cuales se recorren utilizando el método next, el cual nos retorna un objeto que tiene dos propiedades *value* siendo el valor del momento y *done* que es un booleano dependiendo si a terminado o no el ciclo de llamadas

### generadores
es un tipo función que cuando es llamada retorna un iterador y aun siendo llamada no es ejecutada, cada vez que se llama al método next de ese iterador
el valor sera lo que se retorne con la palabra clave *yield* (siendo posible retornar varias veces) tambien podemos utilizar la palabra clave 
*return* pero se dará por terminada la función en el momento que se llege a ella y ignoraran los siguientes llamados a yield después de esta 

``` javascript
function *subeAlRobot(n){

yield `${n} subete al robot`;
yield `${n} ya subete al robot`;

}

let espectador = subeAlRobot('shinji');
console.log(espectador.next());
console.log(espectador.next());
console.log(espectador.next()); //undefined y true
```


### clases
### herencia 
### herencia multiple (No Realmente)
se pueden pasar heredar los métodos a una clase de dos clases padres 
como si se realizase una combinación a las clases que se

``` javascript
class clasePadre {}
class claseHija Extends clasePadre {}
class claseMadre {}
class claseHija Extends clasePadre with claseMadre {}
```


# lo que viene 
### funcion asyc 

las funciones asyc son funciones que retornar el resultado de una promesa
de forma sincrona y sin bloquear el proseso normal del lenguaje 
se utilizan dos palabras claves una asyn y await 
async acompaña a la declaracion de la cabecera 
