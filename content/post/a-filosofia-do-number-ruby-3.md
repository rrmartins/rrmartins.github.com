+++
title = "a filosofia do number ruby 3"
date = "2012-08-08"
slug = "2012/08/08/a-filosofia-do-number-ruby-3"
Categories = ["Ruby API", "Ruby", "The Ruby Programming Language", "Matz"]
+++
<!--more-->
<p>Nessa noite, eu estava assistindo um jogo na tv, e navegando na internet achei um link muito bom(<a href="http://www.artima.com/intv/ruby.html">http://www.artima.com/intv/ruby.html</a>), que já consegui a
autorização para colocar aqui para vocês...</p>

<p>Então, abaixo uma entrevista do criador da linguagem de programação <a href="http://www.ruby-doc.org/core-1.9.3/">Ruby</a>, o <a href="https://twitter.com/yukihiro_matz">Yukihiro Matsumoto 'Matz'</a>.</p>

<h2>A Filosofia do #<a href="http://www.ruby-doc.org/core-1.9.3/">Ruby</a></h2>

<h6>Resumo</h6>

<p><a href="https://twitter.com/yukihiro_matz">Yukihiro Matsumoto 'Matz'</a>, como é conhecido online, é o criador da linguagem de programação <a href="http://www.ruby-doc.org/core-1.9.3/">Ruby</a>. <a href="http://www.ruby-doc.org/core-1.9.3/">Ruby</a> é uma linguagem orientada a objeto adequada para escrever scripts do dia-a-dia, assim como em grande escala de aplicações. Matz começou a trabalhar no <a href="http://www.ruby-doc.org/core-1.9.3/">Ruby</a> em 1993, porque ele queria uma linguagem que o fizesse produtivo enquanto fosse divertido de usar. Inicialmente popular no Japão, <a href="http://www.ruby-doc.org/core-1.9.3/">Ruby</a> tem encontrado seu caminho para os corações de programadores em todo o mundo.</p>

<p>Nesta entrevista, Yukihiro Matsumoto discute a filosofia do design do <a href="http://www.ruby-doc.org/core-1.9.3/">Ruby</a>, as características da linguagem <a href="http://www.ruby-doc.org/core-1.9.3/">Ruby</a>, e se tornar um programador melhor. Neste capítulo inicial, Matz faz filosofias sobre a imperfeição de design, o perigo de <a href="http://pt.wikipedia.org/wiki/Ortogonalidade">ortogonalidade</a>, a concessão de liberdade com a orientação, o princípio da menor surpresa e a importância do ser humano em empreendimentos de computador.</p>
<!--more-->

<h6>Nenhuma Línguagem Perfeita</h6>

<p><b>Bill Venners</b>: Dave Thomas, co-autor de Programming <a href="http://www.ruby-doc.org/core-1.9.3/">Ruby</a>: Um Guia do Programador Pragmático, disse que você não acha que um projeto de linguagem deve ser perfeito. Por que não?</p>

<p><b>Yukihiro Matsumoto</b>: designers de Linguagens querem projetar a linguagem perfeita. Eles querem ser capazes de dizer: "A minha linguagem é perfeita. Ela pode fazer tudo." Mas é simplesmente impossível projetar uma linguagem perfeita, porque existem duas maneiras de olhar para uma mesma linguagem. Uma maneira é olhar para o que pode ser feito com essa linguagem. A outra é olhar para o que sentimos usando essa linguagem, como nos sentimos durante a programação.</p>

<p>Por causa da Teoria da <a href="http://ethosproject.blogspot.com.br/2012/06/preconceito-ignorancia-e-genialidade.html">Integridade de Turing</a>, tudo que uma linguagem pode fazer teoricamente pode ser feito por outra linguagem, mas a um custo diferente. Você pode fazer tudo em <a href="http://pt.wikipedia.org/wiki/Assembly">Assembler</a>, mas ninguém quer programar em assembler mais. Do ponto de vista que você pode fazer, portanto, as línguas diferem entre si, mas as diferenças são limitadas. Por exemplo, <a href="http://www.python.org/">Python</a> e <a href="http://www.ruby-doc.org/core-1.9.3/">Ruby</a> fornecem quase o mesmo poder para o programador.</p>

<p>Em vez de enfatizar o que eu quero enfatizar a parte como: Como nos sentimos durante a programação, essa é a diferença principal do <a href="http://www.ruby-doc.org/core-1.9.3/">Ruby</a> a partir de projetos em outras linguagens. Eu enfatizo a sensação, em particular, como eu me sinto usando <a href="http://www.ruby-doc.org/core-1.9.3/">Ruby</a>. Eu não trabalho duro para tornar <a href="http://www.ruby-doc.org/core-1.9.3/">Ruby</a> perfeito para todos, porque você se sente diferente de mim. Nenhuma linguagem pode ser perfeita para todos. Eu tentei fazer o <a href="http://www.ruby-doc.org/core-1.9.3/">Ruby</a> perfeita para mim, mas talvez ela não é perfeito para você. A linguagem perfeita para Guido van Rossum provavelmente é <a href="http://www.python.org/">Python</a>.</p>

<h6><a href="http://www.dicio.com.br/ortogonal/">Ortogonais</a> em relação harmoniosa</h6>

<p><b>Bill Venners</b>: Dave Thomas também afirmou que, se eu pedir para você adicionar um recurso que é ortogonal, você não vai fazer. O que você quer é algo que seje harmonioso. O que significa isso?</p>

<p><b>Yukihiro Matsumoto</b>: Eu acredito que a consistência e ortogonalidade são ferramentas de design, não o objetivo principal no projeto.</p>

<p><b>Bill Venners</b>: O que significa ortogonalidade neste contexto?</p>

<p><b>Yukihiro Matsumoto</b>: Um exemplo de ortogonalidade é permitir qualquer combinação de características de pequeno porte ou de sintaxe. Por exemplo, <a href="http://pt.wikipedia.org/wiki/C_(linguagem_de_programa%C3%A7%C3%A3o)">C</a> suporta ambos os valores de parâmetro padrão para funções e sobrecarga de nomes de função com base em parâmetros. Ambos são boas características  para se ter em uma língua, mas porque elas são ortogonais, você pode aplicar ao mesmo tempo. O compilador sabe como aplicar ao mesmo tempo. Se é ambígua, o compilador irá sinalizar um erro. Mas se eu olhar para o código, eu preciso aplicar a regra com o meu cérebro também. Eu preciso adivinhar como o compilador funciona. Se eu estiver certo, e eu for inteligente o suficiente, não há problema. Mas se eu não sou inteligente o suficiente, e eu não sou realmente, causa confusão. O resultado será inesperado para uma pessoa comum. Este é um exemplo de como ortogonalidade é má.</p>

<p><b>Bill Venners</b>: Em outras palavras, as características ortogonais irá funcionar uma vez que o escritor do compilador entendê-las e recebe-las para trabalhar. Mas é difícil para os programadores entender quando olham para ele, porque é complicado, porque eu tenho que descobrir como essas duas coisas andam juntas.</p>

<p><b>Yukihiro Matsumoto</b>: As funcionalidades ortogonais, quando combinadas, podem explodir em complexidade.</p>

<p><b>Bill Venners</b>: Então, qual é a alternativa? O que seria mais harmonioso?</p>

<p><b>Yukihiro Matsumoto</b>: Basta pegar um dos dois para colocar na linguagem. Você não tem que fazer tudo o que você pode pensar. Você precisa escolher um deles, mesmo que ambos sejam bons.</p>

<h6>Liberdade e Conforto</h6>

<p><b>Bill Venners</b>: Uma das filosofias de design na comunidade <a href="http://www.python.org/">Python</a> está fornecendo uma e apenas uma maneira de fazer as coisas. Se você fornecer cinquenta maneiras diferentes de fazer a mesma coisa, então você forneceu comodidade para os escritores de código. As pessoas podem escrever coisas da sua melhor forma. A troca é para os leitores de código. Quando eu li o seu código, você poderia ter escrito de um jeito. Quando eu li o código de outras pessoas, elas podem ter escrito de outra forma. Então, como um leitor de eu acabar precisando estar familiarizado com todos os meios para realizar a tarefa, não apenas a minha maneira favorita de escrevê-la. Esse é o dilema do design. A comunidade <a href="http://www.python.org/">Python</a> parece preferir a uma e apenas uma maneira de abordagem, mas <a href="http://www.ruby-doc.org/core-1.9.3/">Ruby</a> parece fornecer várias maneiras de fazer a mesma coisa.</p>

<p><b>Yukihiro Matsumoto</b>: <a href="http://www.ruby-doc.org/core-1.9.3/">Ruby</a> herdou a filosofia <a href="http://www.perl.org.br/Main/WebHome">Perl</a> de ter mais de uma maneira de fazer a mesma coisa. Eu herdei essa filosofia de <a href="http://pt.wikipedia.org/wiki/Larry_Wall">Larry Wall</a>, que é o meu herói, na verdade. Eu quero fazer os usuários de <a href="http://www.ruby-doc.org/core-1.9.3/">Ruby</a> livre. Eu quero dar-lhes a liberdade de escolher. As pessoas são diferentes. As pessoas escolhem diferentes critérios. Mas se há uma maneira melhor entre muitas alternativas, eu quero encorajar esse caminho, tornando-o confortável. Então é isso que eu tentei fazer. Talvez o código do <a href="http://www.python.org/">Python</a> é um pouco mais legível. Todo mundo pode escrever o mesmo estilo de código <a href="http://www.python.org/">Python</a>, por isso pode ser mais fácil de ler, talvez. Mas a diferença de uma pessoa para outra é tão grande, proporcionando apenas uma maneira de ajudar é pouco, mesmo se você estiver usando o <a href="http://www.python.org/">Python</a>, eu acho. Prefiro fornecer muitas maneiras se é possível, mas encorajar ou orientar os usuários a escolher um caminho melhor, se é possível.</p>

<h6>A alegria do <a href="http://www.ruby-doc.org/core-1.9.3/">Ruby</a></h6>

<p><b>Bill Venners</b>: Em um artigo introdutório sobre <a href="http://www.ruby-doc.org/core-1.9.3/">Ruby</a>, você escreveu: "Para mim, o propósito da vida é, em parte, para ter alegria de programadores, que muitas vezes se sentem alegres quando eles podem se concentrar no lado criativo da programação, o <a href="http://www.ruby-doc.org/core-1.9.3/">Ruby</a>, então, é projetado para fazer programadores felizes.. " Como pode o <a href="http://www.ruby-doc.org/core-1.9.3/">Ruby</a> fazer programadores felizes?<p>

<p><b>Yukihiro Matsumoto</b>: Você quer curtir a vida, não é? Se você começa o seu trabalho feito rapidamente e seu trabalho é divertido, isso é bom não é? Esse é o propósito da vida, em parte. Sua vida é melhor.</p>

<p>Eu quero resolver os problemas que encontro no cotidiano usando computadores, então preciso escrever programas. Usando <a href="http://www.ruby-doc.org/core-1.9.3/">Ruby</a>, quero me concentrar nas coisas que faço, e não as regras mágicas da linguagem, como começo com algum público vazio, tenho algo a dizer, "Olá, mundo de impressão." Eu só quero dizer, "imprimir isto!" Eu não quero todas as palavras mágicas circundantes. Eu só quero concentrar-se na tarefa. Essa é a idéia básica. Então eu tentei fazer o <a href="http://www.ruby-doc.org/core-1.9.3/">Ruby</a> conciso e com código suscinto.</p>

<p><b>Bill Venners</b>: permitir que os programadores escrevem códigos que é conciso e suscinto é uma maneira de fazê-los felizes.</p>

<p><b>Yukihiro Matsumoto</b>: Sim, para que eles possam se concentrar no problema em si. Às vezes as pessoas anotam pseudo-código no papel. Se esse pseudo-código é executado diretamente em seus computadores, é melhor, não é? <a href="http://www.ruby-doc.org/core-1.9.3/">Ruby</a> tenta ser assim, como o pseudo-código que é executado. As pessoas dizem que <a href="http://www.python.org/">Python</a> também.</p>

<p><b>Bill Venners</b>: Sim, as pessoas dizem que Pytho é pseudo-código executável. O que mais está em <a href="http://www.ruby-doc.org/core-1.9.3/">Ruby</a> para fazer programadores felizes?</p>

<p><b>Yukihiro Matsumoto</b>: Em nossas vidas diárias como programadores, processamos cadeias de texto muito grandes. Então, eu tentei trabalhar duro em processamento de texto, ou seja, a Classe <a href="http://ruby-doc.org/core-1.9.3/String.html">String</a> e <a href="http://www.ruby-doc.org/core-1.9.3/Regexp.html">Expressões Regulares</a>. As <a href="http://www.ruby-doc.org/core-1.9.3/Regexp.html">Expressões Regulares</a> são incorporadas na linguagem e são muito boas para uso. <a href="http://www.ruby-doc.org/core-1.9.3/">Ruby</a> pode chamar todas as chamadas de sistema em <a href="http://pt.wikipedia.org/wiki/Unix">Unix</a> e mais da API do Windows. Isto traz o poder e função do sistema operacional para o ambiente da linguagem interpretativa. Assim você pode fazer administração de sistemas e programação diária de processamento de texto. Esse é o maior domínio de, pelo menos, a minha vida, então eu trabalhei duro para fazer isso bom.</p>

<p><b>Bill Venners</b>: Então, basicamente, o <a href="http://www.ruby-doc.org/core-1.9.3/">Ruby</a> me ajuda a gozar a minha vida, me ajudando a fazer meu trabalho mais rapidamente e com mais diversão?</p>

<p><b>Yukihiro Matsumoto</b>: Ele me ajuda a fazer isso. Eu não tenho certeza se <a href="http://www.ruby-doc.org/core-1.9.3/">Ruby</a> funciona para você, mas eu espero que sim.</p>

<h6>O Fator Humano</h6>

<p><b>Bill Venners</b>: Em uma entrevista, você disse, " Não subestime o fator humano, ainda penso que nós estamos na frente de computadores, eles são meios que estamos trabalhando para consumo humano, com humana." O que você quer dizer com isso?</p>

<p><b>Yukihiro Matsumoto</b>: Imagine que você está escrevendo um e-mail. Está em frente do computador. Você está operando o computador, clica em um mouse e digita em um teclado, mas a mensagem será enviada a um ser humano através da internet. Então você está trabalhando antes do computador, mas com um ser humano por trás do computador. A maioria das tarefas que fazemos são para seres humanos. Por exemplo, um cálculo do imposto é contar números para que o governo possa tirar dinheiro da minha carteira, mas o governo é composto por seres humanos.</p>

<p>A maioria das nossas tarefas estão relacionadas com os seres humanos, afinal. Assim, na programação, ou pedimos ao computador para trabalhar para um ser humano, ou descrevemos nossos pensamentos para um computador de uma maneira muito clara de que até mesmo o computador possa executar. No primeiro caso, tornando o trabalho do computador para os seres humanos, o alvo é um ser humano através do computador. No segundo caso, a expressão dos nossos pensamentos claramente suficiente para ser entendido e executado por computadores, expressa a intenção de nossos cérebros humanos e, como resultado, é executada pelos computadores. Assim, em ambos os casos, o objeto aqui é humano.</p>

<p><b>Bill Venners</b>: O que é importante pensar dessa forma? Você diz: "Não subestime o fator humano." Por quê?</p>

<p><b>Yukihiro Matsumoto</b>: Porque computadores não se importaria se eu devo fazer o esforço para se comunicar com eles ou se é fácil de se comunicar com eles. Eles não se importam se eu colocar o número de sequências de instruções de bytes em um arquivo e alimentá-lo com eles para correr, ou se uma linguagem de alto nível geradas as instruções. Com os computadores não me importo. Nós, seres humanos se preocupam com o esforço que nós pagamos. Muitas vezes as pessoas, especialmente engenheiros de computação, tem o foco sobre as máquinas. Eles pensam: "Ao fazer isso, a máquina irá correr mais rápido. Ao fazer isso, a máquina vai funcionar mais eficazmente. Ao fazer isso, a máquina algo algo algo." Eles estão se concentrando em máquinas. Mas, na verdade temos de nos concentrar em seres humanos, sobre como os seres humanos se preocupam com fazer a programação e operação da aplicação das máquinas. Nós somos os mestres. Eles são os escravos.</p>

<p><b>Bill Venners</b>: Por enquanto, de qualquer maneira.</p>

<p><b>Yukihiro Matsumoto</b>: Por enquanto de qualquer forma, até a idade terminar.</p>

<h6>Princípio da menor surpresa</h6>

<p><b>Bill Venners</b>: Em uma entrevista, você disse "Eu projetei <a href="http://www.ruby-doc.org/core-1.9.3/">Ruby</a> para minimizar minha surpresa, eu estava muito surpreso quando as pessoas ao redor do mundo me disse que <a href="http://www.ruby-doc.org/core-1.9.3/">Ruby</a>Ruby reduziram a sua surpresa e reforçou a sua alegria de programar. Agora eu tenho certeza de que as mentes dos programadores.. são iguais em todo o mundo. "Por que o princípio da menor surpresa?</p>

<p><b>Yukihiro Matsumoto</b>: Na verdade, eu não fiz a alegação de que <a href="http://www.ruby-doc.org/core-1.9.3/">Ruby</a> segue o princípio da menor surpresa. Alguém sentiu a concepção de que <a href="http://www.ruby-doc.org/core-1.9.3/">Ruby</a> segue a filosofia, então eles começaram a dizer isso. Eu não trouxe o que, na verdade.</p>

<p>Eu queria minimizar minha frustração durante a programação, assim que eu quero minimizar meu esforço na programação. Esse era o meu objetivo principal no projeto <a href="http://www.ruby-doc.org/core-1.9.3/">Ruby</a>. Quero divertir-me na programação. Depois de libertar as pessoas de <a href="http://www.ruby-doc.org/core-1.9.3/">Ruby</a> e muitos ao redor do mundo que conheci <a href="http://www.ruby-doc.org/core-1.9.3/">Ruby</a>, eles disseram que sentem o que sinto. Eles vieram para cima com a frase do princípio da menor surpresa. Mas, na verdade, é muitas vezes incompreendido.</p>

<p><b>Bill Venners</b>: Como é mal compreendido?</p>

<p><b>Yukihiro Matsumoto</b>: Todo mundo tem um fundo individual. Alguém pode vir de <a href="http://www.python.org/">Python</a>, alguém pode vir de <a href="http://www.perl.org.br/Main/WebHome">Perl</a>, e podem ser surpreendido por diferentes aspectos da linguagem. Em seguida, eles vêm até mim e dizer: "Fiquei surpreso com esse recurso da língua, assim, portanto, o <a href="http://www.ruby-doc.org/core-1.9.3/">Ruby</a> viola o princípio da menor surpresa". Espere. Espere. O princípio da menor surpresa não é apenas para você. O princípio da menor surpresa significa princípio, pelo menos da minha surpresa. E isso significa que o princípio da menor surpresa depois que você aprender <a href="http://www.ruby-doc.org/core-1.9.3/">Ruby</a> muito bem. Por exemplo, eu era um programador <a href="http://pt.wikipedia.org/wiki/C%2B%2B">C++</a> antes de começar a projetar <a href="http://www.ruby-doc.org/core-1.9.3/">Ruby</a>. Eu programei em <a href="http://pt.wikipedia.org/wiki/C%2B%2B">C++</a> exclusivamente dois ou três anos. E depois de dois anos de programação <a href="http://pt.wikipedia.org/wiki/C%2B%2B">C++</a>, ele ainda me surpreendeu.</p>

<p>Fonte: <a href="http://www.artima.com">Artima</a></p>

------
<p>
É isso ai amigos.. uma boa entrevista!

Até a proxima! =D</p>
