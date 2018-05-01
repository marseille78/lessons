# Добавить React на существующее приложение

([Документации](../../../Readme.md)/[React.JS](../../Readme__react.md)/[React документация](../../docs.md)/[Установка](../installation.md))

***

*Вам не нужно переписывать свое приложение, чтобы начать использовать React.*

Мы рекомендуем добавлять React в небольшую часть вашего приложения, например отдельный виджет, чтобы вы могли видеть, хорошо ли он подходит для вашего случая использования.

Хотя React [можно использовать](../advanced_guides/react_without_es6.md) без конвейера сборки, мы рекомендуем настроить его, чтобы вы могли быть более продуктивными. Современная сборка обычно состоит из:

* **Менеджер пакетов**, таких как [Yarn](https://yarnpkg.com/uk/) или [npm](https://www.npmjs.com/). Это позволяет вам использовать обширную экосистему сторонних пакетов и легко устанавливать или обновлять их.
* **Сборщики**, такие как [WebPack](https://webpack.js.org/) или [Browserify](http://browserify.org/). Они позволяют писать модульный код и объединять его в небольшие пакеты для оптимизации времени загрузки.
* **Компиляторы**, такие как [Babel](http://babeljs.io/). Они позволяют писать современный JavaScript-код, который по-прежнему работает в старых браузерах.

## Установка React

> Заметка:
> После установки мы настоятельно рекомендуем создать [сборку production-версии](../advanced_guides/optimizing_performance.md), чтобы убедиться, что вы используете быструю версию React в производстве.

Мы рекомендуем использовать [Yarn](https://yarnpkg.com/) или [npm](https://www.npmjs.com/) для управления front-end зависимостями. Если вы новичок в менеджерах пакетов, то [документация Yarn](https://yarnpkg.com/en/docs/getting-started) - это хорошее место для начала работы.

Чтобы установить React with Yarn, выполните:

```
yarn init
yarn add react react-dom
```

Чтобы установить React с npm, запустите:

```
npm init
npm install --save react react-dom
```

И Yarn, и npm загружают пакеты из [реестра npm](http://npmjs.com/).

> **Заметка:**
> Чтобы предотвратить потенциальную несовместимость, все пакеты React должны использовать одну и ту же версию. (Это включает в себя `react`, `react-dom`, `react-test-renderer` и т.д.)

## Включение ES6 и JSX

Мы рекомендуем использовать React with [Babel](http://babeljs.io/), чтобы вы могли использовать ES6 и JSX в своем JavaScript-коде. ES6 - это набор современных функций JavaScript, которые упрощают разработку, а JSX является расширением языка JavaScript, который отлично работает с React.

В [инструкции по установке Babel](https://babeljs.io/docs/setup/) объясняется, как настроить Babel во многих различных средах сборки. Убедитесь, что вы устанавливаете [babel-preset-react](http://babeljs.io/docs/plugins/preset-react/#basic-setup-with-the-cli-) и [babel-preset-env](http://babeljs.io/docs/plugins/preset-env/) включаете их в свою [.babelrc конфигурацию](http://babeljs.io/docs/usage/babelrc/), и хорошей вам работы.

## Hello World с ES6 и JSX

Мы рекомендуем использовать сборщики, такие как [webpack](https://webpack.js.org/) или [Browserify](http://browserify.org/), чтобы вы могли писать модульный код и объединять его в небольшие пакеты для оптимизации времени загрузки.

Самый маленький пример React выглядит так:

```javascript
import React from 'react';
import ReactDOM from 'react-dom';

ReactDOM.render(
  <h1>Hello, world!</h1>,
  document.getElementById('root')
);
```

Этот код превращается в элемент DOM с идентификатором `root`, поэтому вам нужно `<div id="root"></div>` где-то в вашем HTML-файле.

Аналогично, вы можете отобразить компонент React внутри элемента DOM где-то внутри вашего существующего приложения, написанного с помощью любой другой библиотеки пользовательского интерфейса JavaScript.

[Подробнее об интеграции React в приложения с существующим кодом](../advanced_guides/integrating_with_other_libraries.md).

## Полный пример

Вы можете найти пошаговые инструкции, описывающие базовую реализацию с нуля, включая настройки Babel и Webpack [здесь](https://medium.com/@JedaiSaboteur/creating-a-react-app-from-scratch-f3c693b84658).

## Разработка и Production-версия

По умолчанию React содержит много полезных предупреждений. Эти предупреждения очень полезны в разработке.

**Тем не менее, они делают версию разработки React более крупной и медленной, поэтому вы должны использовать производственную версию при развертывании приложения.**

Узнайте, [как определить, работает ли ваш сайт в правильной версии React](../advanced_guides/optimizing_performance.md), и как наиболее эффективно настроить процесс сборки продукции:

* [Создание Production-сборки с помощью React-приложения](../advanced_guides/optimizing_performance.md)
* [Создание Production-сборки с Одностраничными сборками](../advanced_guides/optimizing_performance.md)
* [Создание Production-сборки с помощью бранча](../advanced_guides/optimizing_performance.md)
* [Создание Production-сборки с помощью Browserify](../advanced_guides/optimizing_performance.md)
* [Создание Production-сборки с Rollup](../advanced_guides/optimizing_performance.md)
* [Создание Production-сборки с помощью webpack](../advanced_guides/optimizing_performance.md)

## Использование CDN

Если вы не хотите использовать npm для управления пакетами клиента, `react` и `react-dom` npm пакеты также предоставляют распределения single-file в `npm` папках. См. Страницу [CDN](cdn_links.md) для ссылок.

***

[< Prev](add_react_to_a_new_app.md) - [Next >](cdn_links.md)