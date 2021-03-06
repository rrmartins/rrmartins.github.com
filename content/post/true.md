+++
title = "True, False e Nil"
date = "2012-05-18"
slug = "2012/05/18/true"
Categories = ["Verdadeiro", "Falso", "Nil", "Ruby", "Ruby 1.8", "Ruby 1.9", "The Ruby Programming Language"]
+++
<!--more-->
<p>Continuando os estudos de Ruby, e a leitura do livro The Ruby Programming Language</p>

<p>Hoje vamos continuar falando de True, False e Nil, é hora de nos aprofundar.</p>

<h2>True, False e Nil</h2>

Ruby tem alguma das palavras-chave, as palavras: True, False e nil(nulo). True e False são os dois valores booleanos, e eles
representar a verdade e a falsidade, sim e não, ligado e desligado, de um objeto. nil é um valor especial reservado para indicar
a ausência de valor.

Cada uma dessas palavras-chave avaliada como um objeto especial. True avalia a um objeto que é uma instância de <a href="http://ruby-doc.org/stdlib-1.9.2/libdoc/singleton/rdoc/Singleton.html">Singleton</a> de TrueClass. Da mesma forma, False e nil são exemplos de FalseClass e NilClass. Note que não há nenhuma classe Boolean em Ruby. TrueClass e False Class ambos têm como objeto de sua superclasse.

Se você quiser verificar se um valor é nulo, você pode simplesmente compará-lo a nil, ou usar o método nil?

``` ruby NilClass
o == nil # o é nil
o.nil? # Outra maneira de testar
```

Note que True, False e nil se referem a objetos, e não números. False e nil não são a mesma coisa que 0, e True
não é a mesma coisa que 1. Quando o Ruby exige um valor booleano, nil se comporta como False e qualquer valor diferente de
nil ou False se comporta como True.
