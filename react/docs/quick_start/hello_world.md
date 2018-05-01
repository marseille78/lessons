# Hello World

([Документации](../../../Readme.md)/[React.JS](../../Readme__react.md)/[React документация](../../docs.md)/[Быстрый старт](../quick_start.md))

***

Самый простой способ начать работу с React - использовать [этот пример кода Hello World на CodePen](https://reactjs.org/redirect-to-codepen/hello-world). Вам ничего не нужно устанавливать; вы можете просто открыть его на другой вкладке и следовать примеру, когда мы проходим примеры. Если вы предпочитаете использовать локальную среду разработки, ознакомьтесь с разделом [«Установка»](../installation/try_react.md).

Самый маленький пример React выглядит так:

```javascript
ReactDOM.render(
  <h1>Hello, world!</h1>,
  document.getElementById('root')
);
```

Он отображает заголовок «Hello, world!» На странице.

Следующие несколько разделов будут постепенно вводить вас в использование React. Мы рассмотрим строительные блоки приложений React: элементы и компоненты. Как только вы освоите их, вы сможете создавать сложные приложения из небольших частей многократного использования.

## Примечание по JavaScript

React - это библиотека JavaScript, поэтому мы предположим, что у вас есть базовое понимание языка JavaScript. Если вы не чувствуете себя очень уверенно, мы рекомендуем [обновить ваши знания JavaScript](https://developer.mozilla.org/en-US/docs/Web/JavaScript/A_re-introduction_to_JavaScript), чтобы вы могли легко следовать.

Мы также используем некоторые синтаксисы ES6 в примерах. Мы стараемся использовать его экономно, потому что это все еще относительно новое, но мы рекомендуем вам ознакомиться с [стрелочными функциями](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Functions/Arrow_functions), [классами](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Classes), [шаблонами литералов](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Template_literals), [let](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Statements/let) и [const](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Statements/const) обявления. Вы можете использовать [Babel REPL](https://babeljs.io/repl/#?presets=react&code_lz=MYewdgzgLgBApgGzgWzmWBeGAeAFgRgD4AJRBEAGhgHcQAnBAEwEJsB6AwgbgChRJY_KAEMAlmDh0YWRiGABXVOgB0AczhQAokiVQAQgE8AkowAUAcjogQUcwEpeAJTjDgUACIB5ALLK6aRklTRBQ0KCohMQk6Bx4gA), чтобы проверить, что компилирует код ES6.

***

[Next >](introducing_jsx.md)