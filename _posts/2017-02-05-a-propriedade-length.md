---
layout: post
title: [Arrays]: A propriedade Length
---

A propriedade length retorna o número de elementos de um array.
Um dos usos mais comuns é para a iteração. Por exemplo:

```js
var numbers = [ 10, 20, 30, 40, 50 ];
for (var i = 0; i < numbers.length; i++) {
	console.log(numbers[i]);
}
```

Nesse exemplo, a iteração é feita até que i seja maior que o número de elementos de numbers. Além disso, podemos:

Passar 'um tamanho' para numbers:

```js
numbers.length = 3;
```

Quando consultar de novo, verá que o retorno é:

```js
[ 10, 20, 30 ]
```

Isso acontece pois o array foi sobrescrito, fazendo que o número de elementos seja 3. Ou seja, foi mantido apenas os 3 primeiros elementos. Isso também acontece quando é passado um número maior:

```js
numbers.length = 10;
```

Vejamos o retorno nesse caso:

```js
[ 10, 20, 30, , , , , , ,  ]
```

O que aconteceu foi: O array também foi sobrescrito, porém foi adicionado índices sem valor para que o array tenha 10 elementos.

Isso também acontece quando é passado um índice maior que o tamanho do array. Por exemplo:

```js
numbers[14] = 60;
```

O que irá acontecer é:

```js
[ 10, 20, 30, , , , , , , , , , , , 60 ]
```

Como pode ver, essa propriedade pode fazer mais do que esperava, divirta-se!
