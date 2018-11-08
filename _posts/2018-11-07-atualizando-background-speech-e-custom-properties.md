---
layout: post
title: Atualizando background com SpeechRecognition & Custom Properties
date: 2018-11-07 
tags: javascript
---

Depois de postar um [tutorial em inglês](https://dev.to/karolinedealencar/updating-background-with-speechrecognition--custom-properties-593p) do meu Pen[Atualizando background com Speech Recognition & Custom Properties](https://codepen.io/KarolinedeAlencar/pen/Oxvjve), decidi também postá-lo em português aqui no blog.

Neste Pen utilizo a API de Speech Recognition e Custom Properties do CSS para atualizar o background da tag body. 

Fazer esse exemplo me fez entender melhor como a API de Speech Recognition funciona e como atualizar o valor de uma Custom Properties via JavaScript. Espero que te ajude também.

Agora vamos começar! :)

## HTML Base

```html
<main class="main">
        <h1 class="title">Speak!</h1>
        <p class="description">You need accept the microphone permission!</p>
        <p class="value">Actual value: <span class="color-value" data-js="varValue">palevioletred</span></p>
        <span class="loader"></span>
</main>
```

## CSS Base

```css
:root {
  --color: palevioletred;
  font-size: 16px;
}

@media (max-width: 500px) {

  :root {
    font-size: 12px;
  }

}

body {
  font-family: 'Roboto', sans-serif;
  background-color: var(--color);
}

.main {
  height: 100vh;
  display: flex;
  flex-direction: column;
  justify-content: center;
  padding: 0 .6rem;
  
  color: #232121;
  text-align: center;
  border: 2px solid #232121;
}

.title {
  margin: 0;
  font-size: 4rem;
}

.description {
  margin: 0;
  font-size: 1.4rem;
  font-weight: 300;
}

.value {
  font-size: 3rem;
  font-weight: 300;
}

.color-value {
  font-weight: bold;
}

.loader {
  font-size: 20px;
  font-style: italic;
}
```

Note que estamos declarando a variável **--color** e utilizando seu valor como cor de fundo do body. Essa variável tem um valor inicial, que colocamos também no HTML para sinalizar a cor atual do background. 

Isso é tudo que precisamos para começar a escrever nosso JavaScript. :)

## Tutorial

#### Declarando o Objeto Speech Recognition 

```javascript
window.SpeechRecognition = window.SpeechRecognition || window.webkitSpeechRecognition;
```
*O Chrome da suporte ao Speech Recognition apenas com o prefixo, por isso estamos o utilizando*


#### Definindo uma instância


```javascript
const recognition = new SpeechRecognition();
```

#### Declarando a língua

```javascript
recognition.lang = 'pt-br';
```


#### Começando o reconhecimento

```javascript
recognition.start();
```

#### Atualizando o texto do Loader

Podemos atualizar o texto do loader quando a API começa a "escutar" o aúdio, assim o usuário sabe que a API foi iniciada.


```javascript
recognition.addEventListener('start', () => loader.textContent = 'Detecting...');
```

#### 'Reiniciando' a API

Agora precisamos escutar o evento **end** e reiniciar a API, assim o usuário consegue atualizar a cor de fundo novamente.

```javascript
recognition.addEventListener('end', recognition.start);
```

#### Pegando o resultado da API

Primeiro precisamos escutar o evento **result**

```javascript
recognition.addEventListener('result', e => {
});
```

Então pegar os resultados da API

```javascript
recognition.addEventListener('result', e => {
    const transcript = Array.from(e.results)
        .map(result => result[0].transcript);
});

```

Agora que temos os resultados, precisamos atualizar a cor do background e atualizar seu valor no HTML.


#### Atualizando o valor da variável 

Agora que temos o resultado, vamos atualizar a variável --color:

```javascript
recognition.addEventListener('result', e => {
    document.body.style.setProperty('--color', transcript);
});

```

E depois, atualizar o HTML com o valor atual do background

#### Atualizando o HTML

```javascript
recognition.addEventListener('result', e => {
    span.textContent = transcript;
});
```

#### Removendo o Loader

Também podemos atualizar o loader com um valor vazio, assim o usuário sabe que a cor de fundo já foi atualizada.

```javascript
recognition.addEventListener('result', e => {
    loader.textContent = '';
});
```


### Nosso JavaScript final:

```javascript
window.SpeechRecognition = window.SpeechRecognition || window.webkitSpeechRecognition;

const span = document.querySelector('[data-js="varValue"]');
const main = document.querySelector('.main');
const loader = document.querySelector('.loader');

const recognition = new SpeechRecognition();
recognition.lang = 'pt-br';

recognition.addEventListener('result', e => {
    const transcript = Array.from(e.results)
        .map(result => result[0].transcript)

    document.body.style.setProperty('--color', transcript);
    span.textContent = transcript;
    loader.textContent = '';
});

recognition.addEventListener('start', () => loader.textContent = 'Detecting...');

recognition.addEventListener('end', recognition.start);

recognition.start();
```



