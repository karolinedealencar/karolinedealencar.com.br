---
layout: post
title:  "Arrays: Os métodos push(), pop(), unshift() e shift()"
date:   2017-03-30 07:30:31 -0200
tags: javascript
---

Os métodos **mutáveis (ou seja, modificam o array)** push(), pop(), unshift() e shift() adicionam ou removem itens no início/final de um array. Vamos ver basicamente o conceito de cada um:

## push()

O push() adiciona um ou mais itens no fim de um array e retorna seu tamanho atual.

```js

var pushEx = [1, 2, 3, 4];
pushEx.push(5, 6);
// O retorno será 6, que é o tamanho atual do array.

```

## pop()

O pop() remove o último elemento do array e o retorna.

```js

var popEx = [10, 20, 30, 40];
popEx.pop();
// O retorno será 40, que é o elemento que foi removido.

```

## unshift()

O unshift() adiciona um ou mais itens no início de um array e retorna seu tamanho atual.

```js

var unshiftEx = [5, 10, 15, 20];
unshiftEx.unshift(0, 'Olá');
// O retorno será 6, que é o tamanho atual do array.

```

## shift()

O shift() remove o primeiro elemento de um array e o retorna.

```js

var shiftEx = [2, 4, 6, 8];
shiftEx.shift();
// O retorno será 2, que é o elemento que foi removido.

```
