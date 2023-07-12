---
title: Utilizando Mixins com SCSS para criar breakpoints
published: true
description: Aperfeiçoando a organização do CSS responsivo com mixins e SCSS
tags: CSS, SCSS, Mixins, ResponsiveDesign
---

![sass](https://dev-to-uploads.s3.amazonaws.com/uploads/articles/sz97k9suaryv0xn9v6r0.jpg)


**Sumário**

- [Introdução](#introdução)
- [O que são Breakpoints?](#o-que-são-breakpoints)
- [Criando um Mixin para Breakpoints](#criando-um-mixin-para-breakpoints)
- [Utilizando o Mixin de Breakpoint](#utilizando-o-mixin-de-breakpoint)
- [Exemplo em HTML](#exemplo-em-html)
- [Conclusão](#conclusão)

---

### Introdução

Um dos principais desafios no desenvolvimento web é a criação de um design responsivo que se adapte perfeitamente a todos os tipos de dispositivos. Nesse contexto, o Sass (Syntactically Awesome Stylesheets) e, mais especificamente, o SCSS (Sassy CSS) têm-se mostrado ferramentas poderosas para o controle eficiente de estilos CSS. Uma das funcionalidades mais úteis do SCSS é a capacidade de criar mixins, que são blocos de código reutilizáveis. 

---

### O que são Breakpoints?

Os breakpoints são pontos onde o conteúdo de um site ou aplicativo responde com mudanças de layout para se adaptar a diferentes tamanhos de tela. Eles são essenciais para ajustar a aparência de um site para dispositivos móveis, tablets e desktops.

---

### Criando um Mixin para Breakpoints

O SCSS permite a criação de mixins para encapsular estilos que serão reutilizados. Vejamos como criar um mixin para breakpoints:

```scss
@mixin breakpoint($point) {
  @if $point == small {
    @media (max-width: 600px) { @content; }
  }
  @elseif $point == medium {
    @media (max-width: 900px) { @content; }
  }
  @elseif $point == large {
    @media (max-width: 1200px) { @content; }
  }
}
```

Este mixin permite que você especifique estilos diferentes para três breakpoints diferentes: pequeno, médio e grande. O `@content` permite que você passe blocos de estilos para o mixin, que serão aplicados no breakpoint especificado.

---

### Utilizando o Mixin de Breakpoint

Agora que criamos nosso mixin, vamos usá-lo. Por exemplo, podemos querer alterar a cor do fundo de uma div quando a tela é menor que 600px (small):

```scss
.div-example {
  background-color: blue;

  @include breakpoint(small) {
    background-color: red;
  }
}
```

Neste exemplo, a div terá uma cor de fundo azul em telas maiores que 600px. No entanto, quando a tela for menor que 600px, o mixin irá aplicar o estilo dentro do bloco `breakpoint(small)`, mudando a cor do fundo para vermelho.

---

### Exemplo em HTML

Agora, aplicando isso em HTML, temos:

```html
<div class="div-example">Este é um exemplo de uma div com design responsivo.</div>
```

Com nosso SCSS compilado para CSS e incluído corretamente na página, o exemplo de div responderá de acordo com os tamanhos de tela que definimos anteriormente.

---

### Conclusão

O uso de mixins com SCSS para a criação de breakpoints é uma estratégia eficaz para gerenciar o CSS responsivo. Ela ajuda a manter seu código limpo, legível e fácil de manter, enquanto proporciona uma experiência de visualização otimizada para os usuários, independentemente do dispositivo que estão usando.

Lembre-se, entretanto, que cada projeto é único e pode necessitar de diferentes números ou valores de breakpoint. Adapte essa estratégia às suas necessidades específicas e lembre-se sempre de testar seu design em diferentes dispositivos para garantir uma experiência de usuário consistente e agradável.