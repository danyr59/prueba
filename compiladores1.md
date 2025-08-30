* **concat:**  palabra reservada  
* **converNRtoS:** palabra reservada  
* **converNEtoS:** palabra reservada  
* **converNEtoNR:** palabra reservada  
* **converNRtoNE:** palabra reservada  
* **Paréntesis** (  ): palabra reservada  
* **\[ \](operador para separar variables array)**: palabra reservada.  
* **if**: palabra reservada.  
* **else:** palabra reservada  
* **empty:** palabra reservada  
* **head:** palabra reservada  
* **tail:** palabra reservada  
* **\= (operador de módulo o resto de igual)**: palabra reservada.  
* **Literales numericos enteros**: Cualquier número  entero.  
* **Literales numericos reales**: Cualquier número real.  
* **\- (operador de resta)**: palabra reservada.  
* **\+ (operador de suma)**: palabra reservada.  
* **\* (operador de multiplicación)**: palabra reservada.  
* **/ (operador de división)**: palabra reservada.  
* **% (operador de módulo o resto de división)**: palabra reservada.  
* **and(operador de y)**: palabra reservada.  
* **or (operador de o)**: palabra reservada.  
* **not (operador de negación)**: palabra reservada.  
* **xor:** palabra reservada  
* **val**: palabra reservada.  
* **let**: palabra reservada.  
* **in**: palabra reservada.  
* **fun**: palabra reservada.  
* **print:** palabra reservada.  
* **pair**: palabra reservada.  
* **fst**: palabra reservada.  
* **snd**: palabra reservada.  
* **true**: palabra reservada.  
* **false**: palabra reservada.  
* **\> :** palabra reservada.  
* **\>= :** palabra reservada.  
* **\< :** palabra reservada.  
* **\<= :** palabra reservada.  
* **\!= :** palabra reservada.  
* **\== :** palabra reservada.  
* **Identificadores:** Comienzan con una letra y solo pueden contener cualquier combinación de letras o números.  
* **String**: cualquier cadena de caracteres entre “ ”.  

## Sintaxis

A continuación se muestra la lista de las expresiones con su significado, representación en memoria y su sintaxis:  
 

* **concat:** palabra reservada.  Define una expresión binaria para concatenar 2 cadenas de caracteres. Se representa mediante un árbol con 2 sub árboles como hijos  
* **converNRtoS:** palabra reservada. Define una expresion unitaria que convierte el tipo numero real a string. Se representa con un árbol con un único sub árbol como hijo. Su sintaxis es (**converNRtoS**(e)).  Por ejemplo (**converNRtoS**(10,2)).  
* **converNEtoS:** palabra reservada. Define una expresion unitaria que convierte el tipo numero entero a string. Se representa con un árbol con un único sub árbol como hijo. Su sintaxis es (**converNEtoS**(e)).  Por ejemplo (**converNEtoS**(10)).  
* **converNEtoNR:** palabra reservada. Define una expresion unitaria que convierte el tipo numero entero a real. Se representa con un árbol con un único sub árbol como hijo. Su sintaxis es (**converNEtoNR**(e)).  Por ejemplo (**converNEtoNR**(10)).  
* **converNRtoNE**: palabra reservada. Define una expresion unitaria que convierte el tipo numero real a entero. Se representa con un árbol con un único sub árbol como hijo. Su sintaxis es (**converNRtoNE**(e)).  Por ejemplo (**converNEtoNR**(10,2)).  
* **if:** Define una expresión condicional. Se representa mediante un árbol con 3 sub árboles como hijos. Su sintaxis es (if(e1 condicional e2)(e3)). Las dos primeras expresiones son las que se compararán, la tercera es la expresión en caso verdadero .   
* **else**:  Define una expresión condicional.   
* **emty:** palabra reservada. Define una expresión unitaria que define un array vació. Se representa con un árbol con un único sub árbol como hijo. Su sintaxis es **emty**.  
* **head:** palabra reservada. Define una expresión unitaria que retorna el primer elemento de un array. Se representa con un árbol con un único sub árbol como hijo. Su sintaxis es (**head**(array)).  Por ejemplo (**head**(array)).  
* **tail:** palabra reservada. Define una expresión unitaria que retorna el ultimo elemento de un array. Se representa con un árbol con un único sub árbol como hijo. Su sintaxis es (**tail**(array)).  Por ejemplo (**tail**(array)).  
* **int**: Define un literal entero.   
* **real**: Define un literal entero.  
* **add**: Define una expresión binaria para sumar dos expresiones. Se representa con un árbol con dos sub árboles como hijos. Su sintaxis es (+(e1)(e2)).  Por ejemplo (+(5)(2)).  
* **subract** Define una expresión binaria para restar dos expresiones. Se representa con un árbol con dos sub árboles como hijos. Su sintaxis es (-(e1)(e2)).  Por ejemplo (-(5)(2)).  
* **mul**: Define una expresión binaria para multiplicar dos expresiones. Se representa con un árbol con dos sub árboles como hijos. Su sintaxis es (\*(e1)(e2)). Por ejemplo (\*(5)(2)).  
* **div**: Define una expresión binaria para dividir dos expresiones. Se representa con un árbol con dos sub árboles como hijos. Su sintaxis es (/(e1)(e2)). Por ejemplo (/(5)(2)).  
* **mod**: Define una expresión binaria para calcular el módulo de dos expresiones. Se representa con un árbol con dos sub árboles como hijos. Su sintaxis es (%(e1)(e2)). Por ejemplo (%(5)(2)).  
* **and(operador de y)**: palabra reservada. Se representa mediante un árbol con 2 sub árboles como hijos  
* **or (operador de o)**: palabra reservada.  Se representa mediante un árbol con 2 sub árboles como hijos  
* **not(operador de y)**: palabra reservada. Se representa mediante un árbol con 2 sub árboles como hijos  
* **xor (operador de o)**: palabra reservada.  Se representa mediante un árbol con 2 sub árboles como hijos  
*   
* **id**: Define un identificador.   
* **val**: palabra reservada .Define una expresión binaria para crear un *binding* de una variable. Se representa con un árbol con dos sub árboles como hijos. El primer hijo es la expresión con el identificador y el segundo es la expresión que se le asociará. Su sintaxis es (val(e1)(e2)). Por ejemplo (val(x)(10)).  
* **let**: palabra reservada. Define una expresión que permite hacer un *binding* “local” de una variable para ser usada en un cuerpo dado. Se representa con un árbol con tres sub árboles como hijos. El primer hijo es la expresión con el identificador, el segundo hijo es la expresión que se le asigna a la variable y el tercero es el cuerpo en el cual se utilizará la variable. Su sintaxis es: (let(e1)(e2)(e3)). Por ejemplo:   
  (let(x)(10)(pair(var(x))(20))).  
* **in**: palabra reservada. Define una  unitaria que retorna el true si el elemento pertenece al array. Se representa con un árbol  unitario con un  sub árbol como hijo. Su sintaxis es (**in**(array)).  Por ejemplo (**in**(e)).  
* **fun**: palabra reservada. Define una expresión para crear un *binding* de una función. Una función en el sentido más puro, **recibe un único parámetro.** Si se requieren varios parámetros, se pueden usar pares ordenados para conformar listas de paŕametros para pasarlos juntos en uno solo. Se representa mediante un árbol con tres sub árboles como hijos. El primero de los hijos es el identificador de la función, el segundo el identificador del parámetro formal y el tercero es el cuerpo de la función. Su sintaxis es (fun(e1)(e2)(e3)). Por ejemplo, la función para elevar un entero al cuadrado, podría definirse como sigue: (fun(pow2)(x)(\*(var(x))(var(x)))).  
* **print**: palabra reservada. Define una  unitaria para mostrar por pantalla un string. Se representa con un árbol  unitario con un  sub árbol como hijo  
* **pair**: palabra reservada. Define una expresión binaria para el manejo de pares ordenados. Su sintaxis es (pair(e1)(e2)). Con este tipo de expresión podrían definirse listas, usando como primer argumento una expresión y como segundo argumento otro par, el final de la lista podría ser denotado por la expresión **unit** en el segundo elemento del último par (nótese que la expresión **unit** podría representar la lista vacía); por ejemplo, si quisiéramos representar la lista de enteros \[1, 2, 3\] podríamos escribirla de la siguiente manera: (pair(1)(pair(2)(pair(3)()))). También, si quisiéramos representar la lista vacía, solo podríamos escribir ().  
* **fst**: palabra reservada. Define una expresión unaria para extraer el primer valor de un par ordenado. . Su sintaxis es (fst(e)). Por ejemplo (fst (pair(1)(2)).  
* **snd**: palabra reservada. Define una expresión unaria para extraer el segundo valor de un par ordenado.  Su sintaxis es (snd(e)).  Por ejemplo (snd (pair(1)(2)).  
* **true**:  palabra reservada.  
* **false**: palabra reservada.  
* **\<**: palabra reservada.  
* **\>**: palabra reservada.  
* **\<=**: palabra reservada.  
* **\>=**: palabra reservada.  
* **\!=**: palabra reservada.  
* **\==:** palabra reservada.  
* **String:** palabra reservada.

