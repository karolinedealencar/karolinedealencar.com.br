---
layout: post
title: Array.from() e Array.of()
date: 2017-03-08 07:08:31 -0200
tags: JavaScript
---

## Array.from();

O método Array.from(), introduzido no ECMAScript 2015, converte um array-like
ou iterable object em um array. Há também a possibilidade de passar dois parâmetros
opcionais:


**mapFn**: Uma função map, que é executada em cada elemento do array que está sendo
criado.

**thisArg**: O valor de *this* quando mapFn for executado.

Segue alguns exemplos:

```js

function arrFrom() {
  return Array.from(arguments, function(x) {
    return x * 5;
  });
}
arrFrom(1, 2, 3); // [ 5, 10, 15 ]

```

### Convertendo uma string.

```js

Array.from('Karol'); //[ 'K', 'a', 'r', 'o', 'l' ]

```

## Array.of();

Já o método Array.of(), também introduzido no ECMAScript2015, cria uma instância de Array com um número X de argumentos. Por exemplo:

```js

var arrOf = Array.of(1, 2, 3);

```

Uma grande diferença, quando falamos desse método, é em relação ao
construtor de Array: Enquanto Array(10) retorna uma array com 10 elementos vazios, Array.Of(10) retorna uma array com o número 10. Vejamos um exemplo:

```js

Array.of(5); // [5]
Array(5); // [ , , , ,  ]

```

*Você pode checar o Polyfill e a compatibilidade nos links a seguir.*

**Artigo totalmente inspirado em [Dev Docs - Array.From](http://devdocs.io/javascript/global_objects/array/from) e [Dev Docs - Array.of](http://devdocs.io/javascript/global_objects/array/of).**
