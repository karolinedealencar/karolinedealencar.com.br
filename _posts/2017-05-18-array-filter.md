---
layout: post
title:  "Arrays: Array.filter()"
date:   2017-05-18 07:34:31 -0200
categories: JS
---

O método array.filter() cria um novo array com os elementos que passaram no teste (retornaram true/truthy) da função fornecida. Os parâmetros são:


**Elemento**: O elemento atual

**Index**: Index do elemento atual

**Array**: O array sendo iterado

**thisArg (Opcional)**: Valor a ser utilizado como this


Alguns exemplos:

### Filtrando animais com a cor preta

```js

var animals = [
  {
    name: 'Cat',
    color: 'black'
  },
  {
    name: 'Dog',
    color: 'White'
  },
  {
    name: 'Rabbit',
    color: 'Brown'
  },
  {
    name: 'Raven',
    color: 'black'
  }
];

var blackAnimals = animals.filter(function(animal) {
  return animal.color == 'black';
})

```

### Filtrando músicas do Beatles

```js

var songs = [
  {
    songName: 'Brandy You\'re A Fine Girl',
    band: 'Looking Glass'
  },
  {
    songName: 'Asleep',
    band: 'The Smiths'
  },
  {
    songName: 'Should I Stay Or Should I Go?',
    band: 'The Clash'
  },
  {
    songName: 'Here Comes The Sun',
    band: 'The Beatles'
  },
  {
    songName: 'God Save The Queen',
    band: 'Sex Pistols'
  },
  {
    songName: 'Pet Sematary',
    band: 'Ramones'
  },
  {
    songName: 'All You Need Is Love',
    band: 'The Beatles'
  }
];

var beatlesSongs = songs.filter(function(song) {
  return song.band == 'The Beatles';
});

```
