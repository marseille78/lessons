# Ссылки CDN

([Документации](../../../Readme.md)/[React.JS](../../Readme__react.md)/[React документация](../../docs.md)/[Установка](../installation.md))

*UMD-сборки React и ReactDOM доступны через CDN.*

```javascript
<script crossorigin src="https://unpkg.com/react@16/umd/react.development.js"></script>
<script crossorigin src="https://unpkg.com/react-dom@16/umd/react-dom.development.js"></script>
```

Вышеупомянутые версии предназначены только для разработки и не подходят для production. Минимизированные и оптимизированные производственные версии React доступны по адресу:

```javascript
<script crossorigin src="https://unpkg.com/react@16/umd/react.production.min.js"></script>
<script crossorigin src="https://unpkg.com/react-dom@16/umd/react-dom.production.min.js"></script>
```

Чтобы загрузить определенную версию `react` и `react-dom`, замените `16` на номер версии.

## Для чего атрибут crossorigin?

Если вы используете React из CDN, мы рекомендуем сохранить [crossorigin](https://developer.mozilla.org/en-US/docs/Web/HTML/CORS_settings_attributes) атрибут:

```javascript
<script crossorigin src="..."></script>
```

Мы также рекомендуем проверить, что используемый CDN задает `Access-Control-Allow-Origin`: *HTTP-заголовок:

![](img/cdn-links.png)

Это позволяет улучшить [обработку ошибок](../../blog/error_handling_in_react_16.md) в React 16 и более поздних версиях.

***

[< Prev](add_react_to_an_existing_app.md)