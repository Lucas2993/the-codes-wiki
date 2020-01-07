# Determinar el tipo de dato de una clase parametrizada

Uno de los tipos de datos más complicados para tratar a la hora de manipular clases de manera genérica y dinámica son los tipos parametrizados. Para ilustrar mejor este punto, se puede tomar la definición de una variable. Esta variable será de un tipo muy conocido, **Collection**, el cual es de tipo parametrizado.
```java
Collection<E> collection1;
```
El tipo **E** ilustra el tipo del cual es la clase parametrizada. Por ejemplo si quisiéramos que nuestra variable fuera una colección de cadenas, quedaría de la siguiente manera:
```java
Collection<String> collection1;
```
En este punto, posiblemente podamos decir que nuestra colección es de cadenas, entonces diríamos que el tipo parametrizado es **String**. Ahora existe un problema dentro del manejo genérico y dinámico de clases, posiblemente nuestra definición de variable sea:
```java
Collection<?> collection1;
```
Suponiendo que no es **null** y que tiene elementos. Como podemos saber el tipo de dato parametrizado? Existen dos métodos pero cada uno tiene una serie de condiciones para poder ser aplicado.

## Mediante el uso de ParametrizedType
Existe un tipo de dato que es utilizado para estos casos. El tipo [ParametrizedType](https://docs.oracle.com/javase/8/docs/api/java/lang/reflect/ParameterizedType.html) sirve para obtener información sobre este tipo de datos y así determinar cual es el tipo de dato que efectivamente esta parametrizado. La pregunta en este punto seria, como podemos llegar desde lo que teníamos antes a esta clase? Simple, hay que primeramente obtener la clase y luego obtener el tipo genérico. De igual manera, existe un impedimento en la aplicación de este método, solo es utilizable cuando se trata de un [Field](https://docs.oracle.com/javase/8/docs/api/java/lang/reflect/Field.html) ya que es aquel que se define durante la escritura del código.
