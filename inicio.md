variables

variables de bloque

las variables de bloque funcionan por medio del bloque (alcanse de la variable)

declaración let

funciona por medio de un bloque simplemente una separación por medio de corchetes (simple corchetes o cualquier expresión que los tenga) ya que estos crean el ámbito en el cual se
va a utilizar y solo existe en ese bloque
cuando no podemos alcanzar una variable del tipo var aparece como indefinida cuando no podemos alcanzar una variable tipo let aparece un un error de referencia.

var varibaleGlobal = 5;
{
 let variableDeBloque = 3;

}

const

en si no es una variable es una constante su sintaxis es muy parecida
a las constantes en c++ ( bueno solo tiene la misma palabra reservada)

las constantes son variables que su valor  no cambia, en si no tiene restricción en el valor si no la asignación, por ejemplo en objetos u arrays usted puede cambiarle valores pero
no el tipo.

operador spread/rest

ahora e6 produce un operador llamador spreak o rest dependiendo de donde se va ha utilizar, este operador consiste en tres punto seguidos antes de la variable que se quiera utilizar,
este consiste en dividir o agrupar valores ya sea dividir los valores de un array o agrupar los valores que sobran como parámetros en una función convirtiéndolos en un array.

variables destructuradas

ahora cada vez que creamos objetos o varibles y las igualamos a un objeto estas toman el
valor de la variable que tenga el mismo nombre ahorandonos escribir un par de lineas,
la sintaxis de este tipo de variables es la palabra reservada var seguido de unos corchetes
(es parecido a los objetos literales salvo que no se escribe el valor en el aunque si se
desea hacerlo simplemente se escribe en el el nombre de la propiedad del objeto a la que se desea
igualar)
en los cuales escribirlas variables que queremos crear e igualarlo al objete que queremos que tome
los valores


las funciones en e6  aceptan parámetros con valores por defecto
si se utiliza undefined como parámetro cuando es llamada la función,
se utilizara el valor por defecto de la función.
si lo que se desea es ignorar ese parámetro debe pasarse null como
  parámetroal momento de llamar la función.

también se puede pasar un una función para recuperar el valor por defecto
de una funcion

numero de parámetros
se utiliza  el vector arguments normalmente, pero existe  un problema con esto
si conocemos el nombre de un parámetro. para consegir el resto de los parámetros
debemos recorrer el vector desde la pocicion siguiente del o los  parámetros conocidos
ahora se utiliza un vector llamado numbers la cual es definida como un parametro con tres
puntos antes (...numbers)

propiedad name

ahora se puede llamar la propiedad llamada name la cual retorna una cadena con la cual
es el nombre de la función o de la propiedad en la cual se utilice, en algunos casos retorna
el tipo de método u el nombre de la función padre, por ejemplo en las enlasadas retorna que
esta ligada y el nombre de la función y el el caso de las funciones anónimas retorna anónimo

funciones inmediatamente invocadas

las funciones invocadas de inmediato son funciones anónimas que son inmediatamente invocadas
mientras son pasadas a una variable, esto hace que quede inicializado como un objeto 

funciones de dirección =>

las funciones de flecha son funciones aunque nos e comportan de la misma forma

las flechas no tiene constructor así que botara error cuando se utiliza con el new

el valor this no puede ser cambiado sigue siendo el mismo valor todo el ciclo de vida de la
funcion

no tiene argumentos

las funciones flecha toman un valor (este valor funciona como un parámetro) y con el se pueden
realizar operaciones de forma normal como una función, si se desea se puede pasar mas valores pero
se utilizara un paréntesis y si no tiene ningún valor a pasar simplemente deja los paréntesis vacíos

para crear el cuerpo de las funciones de flechas utilizamos los corchetes pero si queremos retornar
un objeto literal debemos realizarlo entre paréntesis

funciones de nivel de bloque

las funciones de nivel de bloque se utilizan de forma estricta aunque no es obligatorio pero
su comportamiento cambia si no se utilizan de esta forma y siempre que no este igualada a una variable

objetos

objetos literales

en ocasiones cuando queremos crear objetos literales utilizamos variables con el mismo nombre
de la propiedad del objeto esto se llama duplicidad, en e6 se a eliminado y se puede crear
de forma directa solo separando el nombre de la propiedad con comas, ya que en e6 cuando
una propiedad de un objeto literal no tiene valor el motor de e6 busca en el bloque
una variable con el mismo nombre y le asigna el valor

métodos

ya no es necesario utilizar la palabra clave function en los métodos de e6 ahora solo basta con
los paracentesis y  corchetes

object.assing

llega a remplazar los mixins de muchos frameworks.






