# Evidencia 1 - Análisis Léxico

## Descripción

En los métodos computacionales, la capacidad de analizar y procesar lenguajes es necesaria para muchas aplicaciones. En esta evidencia, desarrollaré un analizador léxico para identificar de manera precisa un lenguaje específico siguiendo unas reglas bien definidas.

El lenguaje con el que analizaré esta conformado por símbolos a, b y 1, con algunas restricciones:

- Debe tener solo las combinaciones de a, b y 1.

- No debe tener las subcadenas: "aaaaa" ni "b1b1b1b1b1".

- Debe terminar con la subcadena: "b1".

El análisis léxico es una parte muy importante en la interpretación de los lenguajes, asegura que las entradas cumplan con reglas que se definan. Para poder reconocer estos patrones, voy a hacer uso de dos herramientas:

- Autómatas Finitos Deterministas(DFA): Son máquinas abstractas que reconocen patrones en secuencias de entrada y constituyen la base de los lenguajes regulares en informática. Estos tienen 5 partes principales:
    - Q: Conjunto finito de estados.
    - Σ: Conjunto de símbolos de entrada, que en este caso es: {a, b, 1}.
    - q: Estado inicial.
    - F: Conjunto de estados finales.
    - δ: Función de transición

- Expresiones Regulares(Regex): Es una secuencia de caracteres que forma un patrón de búsqueda utilizada para comprobar si una cadena contiene el patrón de búsqueda especificado.

## Modelos
Ahora, presentaré los dos modelos que utilizaré para el análisis del lenguaje que se me designo: el Autómata Finito Determinista(DFA) y la Expresión Regular(regex). Ambos modelos son muy importantes para la comnporación, ya que ambos tienen sus respectivas características a la hora de representar y analizar los patrones del lenguaje asignado.

- Expresión regular

Tomando en cuenta las restricciones dadas para el lenguaje asignado, contruí la siguiente expresión:

^(?!.*aaaaa)(?!.*b1b1b1b1b1)[ab1]*b1$

A continuación detallaré los elementos que la componen: 
^ : Este simbolo indica el comienzo de la cadena, es decir de nuestra expresión.
(): Se usa para agrupar un conjunto de elementos.
?!: Este combinación de elementos se conoce como 'Zero-width negative lookahead assertion' basicamente hace una verificación de que una determinada secuencia de elementos no se repita posteriormente.
.*: el simbolo '.' indica cualquier caracter  y el simbolo '*' indica cero o mas y se le aplica al caracter anterior, en conjunto significa que permite cualquier combinación de elementos de nuestro abecedario anteriores a la siguiente serie de elementos en este caso 'aaaa' y 'b1b1b1b1b1'
[]*: como se menciono en la anterior expresión, el simbolo '*' lo usamos para indicar cero o mas, los corchetes '[]' los usamos para indicar que cualquier caracter de los corchetes será valido, en conjunto significa que esta permitida cualquier cantidad(cero o más) de los caracteres dentro de de los corchetes, en este caso 'a,b o 1'
$:Este simbolo indica que la subcadena anterior es el final de la cadena, en este caso, la cadena debe terminar con 'b1'.

-Automata 
![Logo](automata.png)






## Referencias:

GeeksforGeeks. (2024, 12 septiembre). Introduction of Finite Automata. GeeksforGeeks. https://www.geeksforgeeks.org/introduction-of-finite-automata/

W3Schools.com. (s. f.). https://www.w3schools.com/python/python_regex.asp

adegeo, gewarren, SeanKilleen, danmoseley, SetTrend, tdykstra, BillWagner, DennisLee-DennisLee, mairaw, Youssef1313, nschonni, nxtn, MizardX, nemrism, ChrisMaddock, Mikejo5000, mjhoffman65, guardrex, 3ventic, svick, tompratt-AQ, yishengjin1413, … (2022, 18 junio). Regular Expression Language - Quick Reference - .NET. Microsoft Learn. https://learn.microsoft.com/en-us/dotnet/standard/base-types/regular-expression-language-quick-reference

Regex cheat sheet. (s. f.). https://www.rexegg.com/regex-quickstart.php






