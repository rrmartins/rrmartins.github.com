+++
title = "um pouco de array no ruby"
date = "2012-05-07"
slug = "2012/05/07/um-pouco-de-array-no-ruby"
Categories = ["Array", "Ruby", "Ruby 1.8", "Ruby 1.9", "The Ruby Programming Language"]
+++
<!--more-->
<p>Continuando os estudos de Ruby, e a leitura do livro The Ruby Programming Language</p>

Um Array é uma seqüência de valores que permite que os valores serem acessados por sua posição, ou índice, na seqüência. Em Ruby, o primeiro valor em um array tem índice 0. Os métodos size e length, retornam o número de elementos em um Array. O último
elemento do Array é no índice de size-1. Valores de índice negativo contar a partir do
final do Array, de modo que o último elemento de uma Array também pode ser acessado
com um índice de -1. O segundo ao último tem um índice de -2,
e assim por diante. Se você tentar ler um elemento além do final de uma Array
(Com um index >= size), ou antes
o início de um Array (com um index < size), Ruby simplesmente retorna nil e não lançará uma exceção.

Arrays de Ruby não são tipados e mutáveis. Os elementos de um Array
não precisam de ser todos da mesma classe, e eles podem ser alterados em qualquer momento.
Além disso, os Arrays são dinamicamente redimensionáveis, você pode acrescentar elementos
a eles e crescer conforme necessário. Se você atribuir um valor a um elemento
além do final do Array, a Array é automaticamente prorrogado com
elementos nil. (É um erro, No entanto, para atribuir um valor para um elemento antes do início de um
Array.)

Uma Array literal é uma lista separada por vírgulas de valores, dentro de
parênteses:

``` ruby Arrays Literal
[1, 2, 3] # Uma Array que contém três objetos Fixnum
[-10 ... 0, 0 .. 10,] # Uma Array de duas faixas; vírgulas extras são permitidos
[[1,2], [3,4], [5]] # Uma Array de Arrayes aninhadas
[X + y, xy, x * y] # array os elementos podem ser expressões arbitrárias
[] # O array vazio tem o tamanho 0
```

Ruby inclui uma sintaxe especial, no caso para expressar literais de Array
cujos elementos são seqüências curtas sem espaços:

``` ruby Arrays
palavras = %w[este é um teste] # O mesmo que: ['este', 'é', 'um', 'teste']
aberto = %w| ( [ { < | # O mesmo que: ['(', '[', '{', '<']
branco = %W(\s \t \r \n) # O mesmo que: ["\ s", "\ t", "\ r", "\ n"]
```

%w e %W introduzir uma Array literal, bem como %q e %Q introduzir uma string literal. Em
particular, as regras delimitadores para %w e %W são as mesmos que para %q e %Q. Dentro dos delimitadores, sem aspas
são necessários em torno das cadeias de elementos do array, e sem vírgulas são
requerido entre os elementos. Elementos do Array são delimitados por espaço em branco.

Você também pode criar Arrays com o construtor Array.new, e isso proporciona
opções de programação inicializando os elementos de Array:

``` ruby Initiallize Array
vazio = Array.new # []: retorna um novo array vazio
nils = Array.new(3) # [nil, nil, nil]: nova Array com 3 elementos nulos
zeros = Array.new(4, 0) # [0, 0, 0, 0]: nova Array com 4 elementos 0
cópia = Array.new(nils) # Faça uma nova cópia de uma Array existente
count = Array.new(3) {| i | i +1} # [1,2,3]: 3 elementos calculado a partir do índice
```

Para obter o valor de um elemento do Array, use um único número inteiro
entre colchetes:

``` ruby Valores com Array
a = [0, 1, 4, 9, 16] # O Array mantém os quadrados dos índices
a[0] # primeiro elemento é 0
a[-1] # O ultimo elemento é de 16
a[-2] # segundo ao último elemento é 9
a[a.size-1] # Outra forma de consultar o último elemento
a[-a.size] # Outra forma de consultar o primeiro elemento
a[8] # Consultando além do fim retorna nil
a[-8] # Consultando antes do início retorna nil, também
```
Todas as expressões acima, exceto para a última, pode também ser
utilizado no lado esquerdo de uma atribuição:

``` ruby Arrays
a[0] = "zero" # a é ["zero", 1, 4, 9, 16]
a[-1] = 1..16 # a é ["zero", 1, 4, 9, 1 .. 16]
a[8] = 64 # a é ["zero", 1, 4, 9, 1 .. 16, nil, nil, nil, 64]
a[-10] = 100 # erro: não é possível atribuir antes do início de um array
```

Como strings, Arrayes também podem ser indexados com dois números inteiros que
representam um índice de partida e um número de elementos, ou um objeto de intervalo. Em qualquer caso, a expressão
retorna o sub-array especificado:

``` ruby Array
a = ('a'..'e').to_a # Faixa convertido para ['a', 'b', 'c', 'd', 'e']
a[0,0] # []: este subarray tem zero elementos
a[1,1] # ['b']: uma Array de um elemento
a[-2,2] # ['d', 'e']: os últimos dois elementos do array
a[0..2] # ['a', 'b', 'c']: os primeiros três elementos
a[-2 .. -1] # ['d', 'e']: os últimos dois elementos do array
a [0 ... -1] # ['a', 'b', 'c', 'd']: a totalidade, mas o último elemento
```

Quando utilizado no lado esquerdo de uma atribuição, um sub-array pode ser
substituído pelos elementos do Array do lado direito. Esta básica
operação funciona para inserções e exclusões, bem como:

```ruby Arrays
a[0,2] = ['A', 'B'] # se torna ['A', 'B', 'c', 'd', 'e']
a[2 ... 5] = ['C', 'D', 'E'] # se torna ['A', 'B', 'C', 'D', 'E']
a[0,0] = [1,2,3] # Inserir elementos no início de a
a[0 .. 2] = [] # Excluir os elementos
a[-1,1] = ['Z'] # Substitua último elemento com outro
a[-1,1] = 'Z' # Para os elementos individuais, a Array é opcional
a[-2,2] = nil # Excluir últimos 2 elementos em 1,8; substituir com nil em 1,9
```

Além disso para o operador colchete para indexar um Array,
a classe Array define uma série de outros operadores úteis. Use + para
concatenar dois Arrays:

```ruby Concatenar Arrays
a = [1, 2, 3] + [4, 5] # [1, 2, 3, 4, 5]
a = a + [[6, 7, 8]] # [1, 2, 3, 4, 5, [6, 7, 8]]
a = a + 9 # erro: lado direito deve ser um array
```

O operador + cria um novo Array que contém os elementos de ambos os seus operandos. Use << para acrescentar um elemento para o final de um
Array existente, e usar a concat anexar os elementos de um array:

``` ruby Array + e concat
a = [] # Comece com uma Array vazia
a << 1 # a é [1]
a << 2 << 3 # a é [1, 2, 3]
a << [4,5,6] # a é [1, 2, 3, [4, 5, 6]]
a.concat [7,8] # a é [1, 2, 3, [4, 5, 6], 7, 8]
```

O operador - subtrai um Array do outro. Começa por fazer uma cópia de sua Array da esquerda,
e, em seguida, remove todos os elementos de que a cópia se que apareçam em qualquer
a Array do lado direito:

``` ruby Array -
['A', 'b', 'c', 'b', 'a'] - ['b', 'c', 'd'] # ['A', 'a']
```

Como a classe String, Array também usa o operador de multiplicação
para a repetição:

```ruby Array *
a = [0] * 8 # [0, 0, 0, 0, 0, 0, 0, 0]
```

A classe Array contem tambem os Operadores booleanos (| , &) e usa-los para a união e
interseção. | Concatena seu argumentos e, em seguida, remove todos os elementos repetidos no resultado.
& retorna uma Array que contém elementos que aparecem em ambas as Arrayes de operando. A Array retornada
não contém elementos duplicados:

``` ruby Array
a = [1, 1, 2, 2, 3, 3, 4]
b = [5, 5, 4, 4, 3, 3, 2]
a | b # [1, 2, 3, 4, 5]: duplicatas são removidas
b | a # [5, 4, 3, 2, 1]: elementos são os mesmos, mas a ordem é diferente
a & b # [2, 3, 4]
b & a # [4, 3, 2]
```

Note-se que estes operadores não são transitivos: a | b não é o mesmo que b | a, por exemplo. Se você ignorar o ordenamento
dos elementos, no entanto, e considerar os Arrays para ser ordenado os conjuntos,
então estes operadores fazem mais sentido. Note também que o algoritmo
que a união e intersecção são realizados não é especificado, e não
existem garantias sobre a ordem dos elementos no retornou dos
Arrays.

A classe Array define um bom número de alguns métodos úteis. O único que vamos discutir aqui é o iterador each, usada para loop através ds
elementos de um Array:

```ruby Array each
a = ('A' .. 'Z').to_a # Comece com uma série de cartas
a.each {| x | print x} # Imprimir o alfabeto, uma letra de cada vez
```

Outros métodos do Array você pode deseja procurar,  incluindo: clear,
compact!, delete_if, each_index, empty?, fill, flatten!, include?, index, join, pop,
push, reverse, reverse_each, rindex, shift, sort, sort!, uniq!, e unshift.

<a href="http://www.ruby-doc.org/core-1.9.2/Array.html">www.ruby-doc.org/core-1.9.2/Array.html</a>

Até a proxima amigos... :)
