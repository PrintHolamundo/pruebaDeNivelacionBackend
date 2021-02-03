# Back End:
Requerimos que desarrolles un proyecto (en node) que detecte si una persona tiene diferencias genéticas basándose en su secuencia de ADN. Para eso es necesario crear un servicio con un método o función con la siguiente firma (En JavaScript/Node JS):

 

boolean hasMutation( String[] dna ); // Ejemplo Java

 

Debe recibir como parámetro un array de Strings que representan cada fila de una tabla

de (NxN) con la secuencia del ADN. Las letras de los Strings solo pueden ser: (A,T,C,G), las

cuales representa cada base nitrogenada del ADN. Debes validar que sólo puedas recibir bases nitrogenadas válidas.

 
###### NO MUTANTE

| A | T | G | C | G | A |
|---|---|---|---|---|---|
| C | A | G | T | G | C |
| T | T | A | T | T | T |
| A | G | A | C | G | G |
| G | C | G | T | C | A |
| T | C | A | C | T | G |

###### MUTANTE

| A | T | G | C | G | A |
|---|---|---|---|---|---|
| C | A | G | T | G | C |
| T | T | A | T | G | T |
| A | G | A | A | G | G |
| C | C | C | C | T | A |
| T | C | A | C | T | G |

Sabrás si un humano es mutante, si encuentras más de una secuencia de cuatro letras
iguales, de forma oblicua, horizontal o vertical.

Ejemplo (Caso mutante):

##### String[] dna = {"ATGCGA","CAGTGC","TTATGT","AGAAGG","CCCCTA","TCACTG"};

En este caso el llamado a la función isMutant(dna) devuelve “true”.
Desarrolla el algoritmo de la manera más eficiente posible.

# Desafíos:
 

Nivel 1:

Servicio en NodeJS que cumpla con el método pedido solicitado.

 

Nivel 2:

Crear una API REST, hostear esa API en un cloud computing libre (Google App Engine, Amazon AWS, etc, en su capa gratuita), crear el servicio “/mutation/” en donde se pueda detectar si existe mutación enviando la secuencia de ADN mediante un HTTP POST con un JSON el cual tenga el

siguiente formato:


POST → /mutation/

{

“dna”:["ATGCGA","CAGTGC","TTATGT","AGAAGG","CCCCTA","TCACTG"]

}

En caso de verificar una mutación, debería devolver un HTTP 200-OK, en caso contrario un 403-Forbidden

 

Nivel 3:

Anexar una base de datos, la cual guarde los ADN’s verificados con la API.Sólo 1 registro por ADN.

Exponer un servicio extra “/stats” que devuelva un JSON con las estadísticas de las verificaciones de ADN: {“count_mutations”:40, “count_no_mutation”:100: “ratio”:0.4}

 

Tener en cuenta que la API puede recibir fluctuaciones agresivas de tráfico (Entre 100 y 1

millón de peticiones por segundo).

 

Debes agregar Test Automáticos, Code coverage > 80%.
## Resultado:

```sh
Para ejecutar:
$ node app.js
```

Ejemplo de uso:
```sh

//Matriz de ADN.
let adn = ['AAAT','CCGG','AAAA','GGCC'];

//Reviso si es mutante o no.
console.log(mutant.isMutant(adn));
```
# Prueba de nivelación
