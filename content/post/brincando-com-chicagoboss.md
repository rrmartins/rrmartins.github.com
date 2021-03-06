+++
title = "brincando com chicagoboss"
date = "2014-05-18"
slug = "2014/05/18/brincando-com-chicagoboss"
Categories = ["Erlang", "ChicagoBoss", "Brincadeira de Criança"]
+++

Uma pequena Introdução:

Se você quiser guardar um segredo, diga a ele para um sueco. Nascido em Stockholm mais de 20
anos atrás, Erlang é a mais avançada plataforma de servidor de código aberto em
existência, mas parece que quase ninguém sabe sobre isso. Erlang pode lidar com
centenas de milhares de conexões simultâneas; ele pode gerar
milhões de processos simultâneos em menos de um segundo; código do servidor pode ser
atualizado, em produção, sem qualquer interrupção do serviço; e erros
são tratados de tal forma que falhas do servidor são extremamente raros.
<!--more-->
O que não gostar? Por que não é todo o mundo de programação em Erlang?
Bem, Erlang é uma linguagem funcional, o que significa que, para implementar qualquer
algoritmo, você deve usar a recursividade em vez dos laços familiares "for" e "while".
Ao contrário de todas as grandes linguagem de script, não há sintaxe embutida
para dicionários ou mapas de hash. E para realmente escrever um servidor funcionando,
você deve aprender com uma camada adicional de magia conhecida como OTP. Estas
barreiras, na minha opinião, têm impedido Erlang de ganhar muita tração fora da Scandinavia.

Mas ChicagoBoss muda tudo isso. O faz Erlang acessível para hackers
que só querem escrever um site confiável em uma linguagem bacana. Usuários do ChicagoBoss
geram código para contornar o histórico hash , e tem o
cuidado com todos os negócios OTP para que você possa se ​​concentrar em escrever as características
o que precisa para o seu site. Quanto aos supostos encargos da programação funcional, acho que a recursividade
raramente é necessária em um dia de trabalho de programação; Eu diria que 99% do código de um aplicativo de servidor
simplesmente transporta dados para e de um banco de dados, de modo que no curso da construção de um
website, o programador processual caminhe dificilmente perca o seu laço "do/while".

Se você é um programador web experiente, você provavelmente vai desfrutar de toda a
amenidades que CB tem para oferecer: um ORM avançado com suporte para
associações de bancos de dados, sharding e caches; modelos velozes compilado até Erlang bytecode;
recompilação automática e no navegador, relatório de erros; directivas simples para recargas e redirecionamentos;
rotas para construção de URLs e tratamento dos pedidos; quadros completos para envio
e recebimento de e-mail; uma fila de mensagens embutida; um quadro para a escrita
e execução de testes funcionais.

No final, através da combinação da plataforma de Erlang com as suas próprias inovações,
ChicagoBoss faz sites um deleite para desenvolver e implantar uma alegria.
Aplicações saliência pode ser escrito no mesmo tempo ou menos equivalentes
Rails aplicações , e eles quase nunca irá travar ou perda de memória . desde
a rede subjacente é tudo assíncrona, você pode facilmente escrever
serviços concorrentes , como o bate-papo , que antes eram só é possível em
estruturas à base de retorno de chamada (como Nginx , Node.js , Torcido, ou Perlbal ) .

A importância deste avanço não pode ser exagerada . É agora
viável para uma pequena equipe para desenvolver e operar um banco de dados -driven,
site altamente interativo , com muito trânsito , com muito pouco investimento de capital .
Embora Chicago chefe não posso te dizer como adquirir os usuários , o resto desta
manual irá mostrar-lhe tudo o que você precisa fazer para lidar com os seus pedidos
e (com sorte) cumprir seus desejos.
