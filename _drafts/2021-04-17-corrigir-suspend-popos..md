---
layout: post
title: Pop!_os - corrigir recuperação de suspensão
date: 2021-04-17
author: Paulo
categories: linux, pop!_os, MSI
---

No meu portátil MSI GF65 Thin 10SER, instalei o POP!_OS 20.10, assim que o adquiri, sendo neste momento um dos SO's que uso quase diariamente.

Esta distribuição funciona muito bem, oferencendo uma experiência de utilização muito boa, nomeadamente a possibilidade de fazer a mudança entre a placa grafica integrada e a NVIDIA de uma forma muito simplificada, além de, para quem dá valor a essa vertente, tem uma aparência muito agradável.

Apesar de todas estas questões, existia apenas uma situação que estragava toda esta agradável experiência de utilização.

Normalmente durante a minha utilização, passam-se por vezes semanas, em que não desligo completamente o meu computador, suspendendo o mesmo quando não preciso de usar, ou quando preciso de me deslocar, sendo que provavelmente as únicas situações que me levam a desligar o mesmo, será decorrente de alguma atualização que assim o exija.
Esta forma de trabalhar, estava a ser colocada em causa, pelo simples facto de que quando suspendia este portátil, ao recuperar da suspensão, não conseguia recuperar a minha sessão, obrigando invariavelmente a reiniciar o portátil.

Após alguma pesquisa, encontrei no github do pop!_os um problema reportado ainda em 2018 (#349)[https://github.com/pop-os/pop/issues/349] com uma indicação da opção a adicionar nas opções de boot do kernel que permitia resolver esta questão.

Assim e após adicionar a opção "mem_sleep_default=deep", com o comando kernel stub, consegui recuperar apenas uma vez.

Depois de investigar sobre quais as possiveis razões para que tal acontecesse, apercebi-me que tinha uma particularidade. O ecrã do portátil, estava configurado para uma resolução que não era a nativa e na realidade o problema, não era o portatil bloquear, mas apenas ficava preto, deixando por exemplo alterar entre os ttys através das teclas de atalho CTRL+Fn. Era desta forma que eu costumava reiniciar portátil.

Experimentei então a colocar novamente o ecrã para a resolução nativa e desde então a situação não voltou a acontecer.

o Pop!_OS é uma distribuição que tem algumas particularidades que costumava procurar no i3, nomeadamente o tiling e a utilização dos atalhos de teclado para gerir as janelas.

A experiência de utilização é bastante agradável.


