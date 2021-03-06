+++
title = "ranges ruby 1 dot 9 2 part i"
date = "2012-05-13"
slug = "2012/05/13/ranges-ruby-1-dot-9-2-part-i"
Categories = ["Range", "Ruby", "Ruby 1.8", "Ruby 1.9", "The Ruby Programming Language"]
+++
<!--more-->
<p>Continuando os estudos de Ruby, e a leitura do livro The Ruby Programming Language</p>

<p>Hoje vamos falar um pouco de Range, é hora de nos aprofundar.</p>

<h2>Ranges</h2>

Um objeto Range representa os valores entre um valor de início e um valor final. Range literais são escritas pela colocação de dois ou três pontos entre o início e o valor fim. Se dois pontos são usados, então o intervalo é inclusivo e o valor final é parte do intervalo. Se três pontos são usados, então o intervalo é exclusiva e o valor final não é parte do range:

``` ruby Range
1..10 # Os números inteiros de 1 a 10, incluindo 10
1...10 # Os números entre 1 e 10, excluindo-se 10
```

Testar se um valor está incluído em um intervalo com o método include? (mas ver abaixo para uma discussão de alternativas):

``` ruby Range
cold_war = 1945 .. 1989
cold_war.include? DateTime.now.year
```

O que esta implícita na definição de um intervalo é a noção de ordem. Se um intervalo são os valores entre dois pontos,
há, obviamente, deve ser alguma forma para comparar os valores para os pontos de extremidade. Em Ruby, isso é feito
com o operador de comparação <=>, que compara seus dois operandos e avalia a -1, 0 ou 1, dependendo da sua ordem relativa
(ou igualdade). Classes, tais como números e strings que têm uma ordenação definir o operador <=>. o
valor só pode ser utilizado como um ponto de extremidade do intervalo se ele responde a esta
operador. Os pontos de extremidade de um intervalo e os valores "em" range são
tipicamente, todos da mesma classe. Tecnicamente, no entanto, qualquer valor que é
compatível com o <=> operador do ponto da extremidade do range pode ser considerado um membro do intervalo.

O objetivo primário para os ranges é comparação: para ser capaz de determinar se um valor está dentro ou fora do range. Um importante
objetivo secundário é a iteração: se a classe dos parâmetros de um range definido um método succ (por sucessor), então existe um conjunto discreto de membros de intervalo, e eles podem
ser repetido a cada passo, e métodos de Enumerable. Considere o intervalo 'A' .. 'c', por exemplo:

```ruby Range
r = 'a' .. 'c'
r.each {|l| print "[#{l}]"} # imprime "[a] [b] [c]"
r.step(2) {|l| print "[#{l}]"} # imprime "[a] [c]"
r.to_a # => ['a', 'b', 'c']: Enumerable define to_a
```

A razão pela qual isto funciona é que a classe String define um método succ e 'a'.succ é 'b' e 'b'.succ é 'c'. Intervalos que
podem ser iterados como este, são intervalos discretos. Faixas cuja ponto final não definem um método succ não pode ser iterada,
e assim eles podem ser chamadas de contínua. Note-se que os intervalos com terminais inteiros são discretos, mas números de ponto flutuante como ponto final são contínuas.

Faixas com terminais inteiros são os mais comuns de serem usados ​​em programas típicos de Ruby. Porque eles são discretos, os ranges inteiros podem sasurusados para cordas de índice e matrizes. Eles são também uma forma conveniente para
representam uma coleção enumerável de valores ascendentes. Observe que o código atribui um range literal a uma variável, e
em seguida, chama métodos no intervalo através da variável. Se você quiser ou
invocar diretamente em uma ampla literal, você deve colocar parênteses o literal, ou a invocação do método é na verdade sobre o ponto final da variavel, em vez de o objecto range em si:


``` ruby Range
1 .. 3.to_a # tenta chamar to_a sobre o número 3
(1 .. 3). To_a # => [1,2,3]
```

Até a proxima!!!
