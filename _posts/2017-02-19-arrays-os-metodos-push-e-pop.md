---
layout: post
title:  "Arrays: Os métodos Push e Pop"
date:   2017-02-19 20:29:31 -0200
categories: JS
---
Os métodos push() e pop() são 'contrários', pois enquanto um adiciona items no fim do array, o outro remove. Vamos ver basicamente o conceito de cada um:

## push()

O push() adiciona valores ao fim do array e retorna seu respecitivo tamanho, por exemplo:

```js
var arr = [1, 2, 3, 4];
arr.push(5, 6);
```

O retorno será 6, que é o tamanho atual da arr.

## pop()

O pop() remove o último item da array e retorna, seguindo o mesmo código, vamos remover o número 6:

```js
// array tem o valor [1, 2, 3, 4, 5, 6];
arr.pop();
```

O retorno será 6, que é o último valor da array.
