Manual simple javascript es6
==================================

# variables

### variables de bloque

las variables de bloque funcionan por medio del bloque que consiste en dos corchetes el cual nos permite manejar el scope de mejor forma vienen siendo similares a las funciones auto ejecutables (alcanse de la variable)
``` [javascript]
{
	let uno = 1;	
	// todo lo que se instancie en este bloque
	// solo sera accesible en el bloque
}
``` 

### declaración let

funciona por medio de un bloque simplemente una separación por medio de corchetes (simple corchetes o cualquier expresión que los use) ya que estos crean el ámbito en el cual se
va a utilizar y solo existe en ese bloque
cuando no podemos alcanzar una variable del tipo var aparece como indefinida cuando no podemos alcanzar una variable tipo let aparece un un error de referencia.
``` [javascript]
var varibaleGlobal = 5;
{
 	let variableDeBloque = 3;
}
``` 
### const

su sintaxis es muy parecidaa las constantes en c++ ( bueno solo tiene la misma palabra reservada)
las constantes son variables que su valor  no cambia, en si no tiene restricción en el valor si no la asignación, por ejemplo en objetos o vectores usted puede cambiarle valores internos perono el tipo con el que fue declarado.

### operador spread/rest (resta)

ahora e6 produce un operador llamador spreak o rest dependiendo de donde se va ha utilizar, este operador consiste en tres punto seguidos antes de la variable que se quiera utilizar,
este consiste en separar o agrupar valores, ya sea separar los valores de un array o agrupar parametros ingresados en una funcion y convertirlos en un vector.

``` [javascript]

function	sumaLoQueSeEnvie(...parametros){
  let temp = 0;
  console.log(parametros);
  parametros.forEach((e) => {
  	temp += e; 
  });
  return  temp;
}
sumaLoQueSeEnvie(1,2,3,4);
// 10
	

``` 

### variables destructuradas

el destructurado funciona separando valores de un vector o un objeto siendo posible guardarlos variables separadas ahorandonos escribir un par de lineas, 
suena similar al operador de tres puntos pero funcionan diferente, su sintaxis se utiliza al momento de la declaracion de una o varias variables,
si queremos destructurar un objeto envolvemos nuestras variables con llaves {} y queremos destructurar un array las envolvemos 
entre corchetes []
``` [javascript]

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
si se desea dejar saltar un valor se deja una coma como representacion de ese valor que no se va ha tomar,
tamben se puede combinar con objetos mucho mas elavorados esto se  conoce como destructuracion anidada combinando las dos formas de destruturar e incluso con el operador de tres puntos, 
en casos expeciales si un valor experado no es retornado por el objeto podemos dejarle un valor por defecto 
y por ultimo tambien podemos utilizar la destructuracion cuando estamos definiendo parametros de funciones 
``` [javascript]

function cuenta({carne,pollo=3}){
  return carne+pollo;
}

var empanadas = {
  carne: 10,
  pollo:5
};


cuenta(empanadas);
``` 

### funciones de dirección o flecha =>

las funciones de flecha son funciones aunque nose comportan de la misma forma que una funcion normal
las flechas no tiene constructor así que botara error cuando se utiliza con el el operardor de instancia new
en las funciones de flecha el valor this no puede ser cambiado, sigue siendo el mismo valor todo el 
ciclo de vida de la funcion

no tiene argumentos

las funciones flecha toman un valor (este valor funciona como un parámetro) y con el se pueden
realizar operaciones de forma normal como una función, si se desea se puede pasar mas valores pero
se utilizara un paréntesis y si no tiene ningún valor a pasar simplemente deja los paréntesis vacíos

para crear el cuerpo de las funciones de flechas utilizamos los corchetes pero si queremos retornar
un objeto literal debemos realizarlo entre paréntesis

funciones de nivel de bloque

las funciones de nivel de bloque se utilizan de forma estricta aunque no es obligatorio pero
su comportamiento cambia si no se utilizan de esta forma y siempre que no este igualada a una variable

### valores de parametros por defecto 

ahora en las funciones se pueden asignar valores por defecto a los pametros, asi cuando falta un parametro
queda por defecto con el valor dado

``` [javascript]

function a(b = 3, d =5){
	return a + d;
}	

a(); // 8

``` 


# objetos

## objetos literales

en ocasiones cuando queremos crear objetos literales utilizamos variables con el mismo nombre
de la propiedad del objeto esto se llama duplicidad, en e6 se a eliminado y se puede crear
de forma directa solo separando el nombre de la propiedad con comas, ya que en e6 cuando
una propiedad de un objeto literal no tiene valor el motor de e6 busca en el bloque
una variable con el mismo nombre y le asigna el valor
``` [javascript]
	
var a = 2,b = 3;
var obj = {
	a, b;
}
	
``` 

tambien las funciones en objetos literales no es necesario utilizar la palabra reservada 'function'

## setter/getter

son un par de funciones para obtener y retornar un valor que funcionan con las palabras reservadas set and get
pero no son llamadas como una funcion si no como una propiedad más 

## propiedad con nombre computalizada 

son las propiedades las cuales su nombre esta creado por medio de un cadenas, siendo posible sumar uno o más de
cadenas   

``` [javascript]
var color = {
  ['eva01']:'morado'
};

console.log(color.eva01);
``` 
### nombre de propiedades

ahora se puede utilizar la palabra reservada 'name' para para obtener una cadena con el nombre de una metodo,
en algunos casos retorna el tipo de método u el nombre de la función padre, por ejemplo en las enlasadas retorna que
esta ligada y el nombre de la función y el el caso de las funciones anónimas retorna anónimo

funciones inmediatamente invocadas

las funciones invocadas de inmediato son funciones anónimas que son inmediatamente invocadas
mientras son pasadas a una variable, esto hace que quede inicializado como un objeto 

## object.assing

llega a remplazar los mixins de muchos frameworks.






