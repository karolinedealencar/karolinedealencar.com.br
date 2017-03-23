---
layout: post
title: "Arrays: Array.fill()"
date: 2017-03-14 07:08:31 -0200
categories: JavaScript
---


## Array.fill();

Array.fill() é um método mutável (ou seja, modifica o objeto) que preenche um array com um valor estático baseando-se no índice inicial/final. Ele recebe três parâmetros:


**Value: O valor que irá preencher o array.**

**Start (opcional): O índice inicial.**

**End (opcional): O índice final.**

*O valor padrão de start é 0 e do end o tamanho do objeto.*

Agora vejamos um exemplo:

```js

[1, 2, 3, 4, 5].fill('Teste', 1, 3);
//O retorno será [ 1, 'Teste', 'Teste', 4, 5 ];

```

Há a possibilidade de passar valores negativos para start e end.
O cálculo é feito da seguinte forma: O tamanho do array (length)
\+ Valor do start/end. Por exemplo:

```js

[1, 2, 3, 4, 5, 6, 7, 8, 9, 10].fill('Olá', -4, -2);
//O retorno será [ 1, 2, 3, 4, 5, 6, 'Olá', 'Olá', 9, 10 ];

```

O que aconteceu aqui foi: Ao colocarmos o valor de start como -4, foi pego o tamanho do array **(que é 10) + -4**, ou seja: **6**. O mesmo ocorreu com o valor de end: **10 + -2 = 8**.


*Você pode checar o Polyfill e a compatibilidade nos links a seguir.*

**Artigo totalmente inspirado em [Dev Docs - Array.fill](http://devdocs.io/javascript/global_objects/array/fill)**
