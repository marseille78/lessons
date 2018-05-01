# Представление JSX

([Документации](../../../Readme.md)/[React.JS](../../Readme__react.md)/[React документация](../../docs.md)/[Быстрый старт](../quick_start.md))

***

Рассмотрим это объявление переменной:

```javascript
const element = <h1>Hello, world!</h1>;
```

Синтаксис этого смешного тега не является ни строкой, ни HTML.

Он называется JSX, и это расширение синтаксиса JavaScript. Мы рекомендуем использовать его с React для описания того, как должен выглядеть пользовательский интерфейс. JSX может напомнить вам о языке шаблонов, но он поставляется с полной мощью JavaScript.

JSX создает «элементы» React. Мы рассмотрим их перевод в DOM в [следующем разделе](rendering_elements.md). Ниже вы можете найти основы JSX, необходимые для начала работы.

## Почему JSX?

Реагирует на то, что логика визуализации по сути связана с другой логикой пользовательского интерфейса: как обрабатываются события, как изменяется состояние со временем и как данные подготовлены для отображения.

Вместо того, чтобы искусственно отделять *технологии*, добавляя разметку и логику в отдельные файлы, React [разделяет *составляющие*](https://en.wikipedia.org/wiki/Separation_of_concerns) с слабо связанными элементами, называемыми «компонентами», которые содержат оба. Мы вернемся к компонентам в [следующем разделе](components_and_props.md), но если вы еще не устраиваете разметку в JS, [этот разговор](https://www.youtube.com/watch?v=x7cQ3mrcKaY) может убедить вас в другом.

React [не требует](../advanced_guides/react_without_jsx.md) использования JSX, но большинство людей считают его полезным в качестве наглядного пособия при работе с пользовательским интерфейсом внутри кода JavaScript. Он также позволяет React показывать более полезные сообщения об ошибках и предупреждения.

С этим давайте начнем!

## Встраивание выражений в JSX

Вы можете встроить любое [выражение JavaScript](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide/Expressions_and_Operators#Expressions) в JSX, обернув его фигурными фигурными скобками.

Так, например, `2 + 2`, `user.firstName` и `formatName(user)` все действительные выражения:

```javascript
function formatName(user) {
  return user.firstName + ' ' + user.lastName;
}

const user = {
  firstName: 'Harper',
  lastName: 'Perez'
};

const element = (
  <h1>
    Hello, {formatName(user)}!
  </h1>
);

ReactDOM.render(
  element,
  document.getElementById('root')
);
```

[Попробуйте это на CodePen](https://reactjs.org/redirect-to-codepen/introducing-jsx).

Мы разделяем JSX на несколько строк для удобства чтения. Хотя это не требуется, при этом мы также рекомендуем обертывать его в круглых скобках, чтобы избежать ловушек [автоматической точки с запятой](http://stackoverflow.com/q/2846283).

## JSX - это выражение тоже

После компиляции выражения JSX становятся регулярными вызовами функций JavaScript и оцениваются для объектов JavaScript.

Это означает, что вы можете использовать JSX внутри `if`cоператоров и `for` циклов, назначать его переменным, принимать его как аргументы и возвращать из функций:

```javascript
function getGreeting(user) {
  if (user) {
    return <h1>Hello, {formatName(user)}!</h1>;
  }
  return <h1>Hello, Stranger.</h1>;
}
```

## Определение атрибутов с помощью JSX

Вы можете использовать кавычки для указания строковых литералов в качестве атрибутов:

```javascript
const element = <div tabIndex="0"></div>;
```

Вы также можете использовать фигурные скобки для вставки выражения JavaScript в атрибут:

```javascript
const element = <img src={user.avatarUrl}></img>;
```

Не помещайте кавычки вокруг фигурных скобок при встраивании выражения JavaScript в атрибут. Вы должны либо использовать кавычки (для строковых значений), либо фигурные скобки (для выражений), но не оба в одном и том же атрибуте.

> **Предупреждение:**
> Поскольку JSX ближе к JavaScript, чем к HTML, React DOM использует `camelCase` соглашение об именовании свойств вместо имен атрибутов HTML.
> Например, `class` становится [className](https://developer.mozilla.org/en-US/docs/Web/API/Element/className) в JSX и `tabindex` становится [tabIndex](https://developer.mozilla.org/en-US/docs/Web/API/HTMLElement/tabIndex).

## Определение детей с помощью JSX

Если тег пуст, вы можете немедленно его закрыть `/>`, например XML:

```jsx
const element = <img src={user.avatarUrl} />;
```

Теги JSX могут содержать дочерние элементы:

```jsx
const element = (
  <div>
    <h1>Hello!</h1>
    <h2>Good to see you here.</h2>
  </div>
);
```

##JSX предотвращает инъекционные атаки

Безопасно встраивать пользовательский ввод в JSX:

```jsx
const title = response.potentiallyMaliciousInput;
// This is safe:
const element = <h1>{title}</h1>;
```

По умолчанию React DOM [избегает](https://stackoverflow.com/questions/7381974/which-characters-need-to-be-escaped-on-html) любых значений, встроенных в JSX, перед их рендерингом. Таким образом, он гарантирует, что вы никогда не сможете вводить все, что явно не написано в вашем приложении. Перед преобразованием все преобразуется в строку. Это помогает предотвратить атаки [XSS (межсайтовые скрипты)](https://en.wikipedia.org/wiki/Cross-site_scripting).

## JSX представляет объекты

Babel компилирует JSX в так называемые `React.createElement()`.

Эти два примера идентичны:

```jsx
const element = (
  <h1 className="greeting">
    Hello, world!
  </h1>
);
```

```jsx
const element = React.createElement(
  'h1',
  {className: 'greeting'},
  'Hello, world!'
);
```

`React.createElement()` выполняет несколько проверок, чтобы помочь вам писать код без ошибок, но по существу он создает такой объект:

```jsx
// Note: this structure is simplified
const element = {
  type: 'h1',
  props: {
    className: 'greeting',
    children: 'Hello, world!'
  }
};
```

Эти объекты называются элементами «Реагировать». Вы можете думать о них как о описаниях того, что вы хотите видеть на экране. React читает эти объекты и использует их для построения DOM и обновления его.

Мы рассмотрим рендеринг элементов React в DOM в следующем разделе.

> Итого:
> Мы рекомендуем использовать определение языка [«Babel» для вашего редактора](http://babeljs.io/docs/editors), чтобы как ES6, так и JSX-код были правильно выделены. Этот веб-сайт использует цветовую схему [Oceanic Next](https://labs.voronianski.com/oceanic-next-color-scheme/), которая совместима с ней.

***

[< Prev](hello_world.md) - [Next >]