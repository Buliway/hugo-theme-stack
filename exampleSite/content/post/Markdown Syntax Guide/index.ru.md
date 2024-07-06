---
title: Синтаксис для написания статей
description: Описание markdown для написания статей в этой теме Hugo
date: 2024-06-28
categories: [
    software, paper
]
tags: [
    web, hugo
]
links:
  - title: Boosty
    description: Поддержать меня на Boosty
    website: https://boosty.to/buliway
    image: /boosty.png
series: ["Hugo Guide"]  # Серия статей на какую-то тему
math: true              # Вкл/Выкл KaTeX рендеринг
# lastmod:              # Дата редактирования поста
# image: string         # Изображение поста
# comments: false       # Вкл/Выкл комментариев под данным постом  
# toc: false            # Вкл/Выкл навигацию по заголовкам справа от поста
# keywords: []string    # Keywords of the page. Useful for SEO.
# draft: true           # Если вкл, то не рендерит эту страницу. Для недописанных постов
---

## Введение

Эта статья содержит в себе сборник всех изначально встроенных статей в эту тему Hugo. Тут будет всё о markdown для написания статей. Как именно это написать в `.md` файле я показывать буду лишь частично. Полностью можно посмотреть в [файле на github](https://raw.githubusercontent.com/Buliway/hugo-theme-stack/master/exampleSite/content/post/Markdown%20Syntax%20Guide/index.ru.md). Эта статья скорее для меня как для админа, чтоб я мог вернуться и глянуть как пишется какой-либо функционал.

В начале статьи надо добавить поле, которое называется [frontmatter](https://gohugo.io/content-management/front-matter/). В документации написаны все возможные параметры, которые туда можно написать. Выделить настройки можно либо через `---`, либо через `+++`. Разница в том, что `---` будет иметь синтаксис `yaml` формата, а `+++` будет иметь синтаксис `toml`. В настройки, например, можно добавить поле `series = ["Themes Guide"]`. Это будет означать серию статей о какой-то теме, чтоб читатели могли видеть связанный контент. Как я понимаю, речь про рекомендации в конце поста. Хотя рекомендации, в теории, должны работать и без этого, просто по общим категориям и тегам.

Справа есть навигация по заголовкам. Её можно выключить, если в начало файла добавить `toc: false`. В этой навигации отображаются только заголовки 2-4 уровней. Глубже не отобразит. Но это всё можно поменять в `hugo.yaml`.

Изначально описание статьи, которое отображается на главной странице, пишется в начале файла в графе `description`. Но можно включить режим, когда в описание помещается маленькая часть начала статьи. Для такого сценария есть свой синтаксис, который требует написать \<\!\-\-more\-\-\> в том месте, до которого должно быть описание поста.

Внутри markdown можно писать html код для изменения визуала. Например, <span style="background: #FF5582A6;color:black">я могу покрасить этот текст в чёрный на розовом фоне</span> так:
```html
<span style="background: #FF5582A6;color:black">я могу покрасить этот текст в чёрный на розовом фоне</span>
```

Если символ используется для markdown, но его хочется написать как есть, без использования в форматировании текста, то надо использовать `\` перед ним. Я так поступил с примером выше, который изначально выглядит так: `\<\!\-\-more\-\-\>`.

Чтоб оставить ссылку на другой пост, я предпочитаю пользоваться абсолютными путями относительно каталога `content`. Например, если я хочу ссылаться на пост, который находится в `content/page/Архивы`, то мне надо написать [так]({{< ref "/page/Архивы" >}}), что в markdown будет выглядеть \[так\]\(\{\{\< ref "/page/Архивы" \>\}\}\). Оно будет работать даже в том случае, если в каталоге `Архивы` будет находиться несколько `.md` файлов для разных языков. Он отправит на ту страницу, язык которой выбран у пользователя в настройках.


Разделитель текста, который используется внизу, пишется через `---` с новой строки. Над и под ним строки должны быть пустыми.

---

## Стандартный Markdown

### Заголовки

Заголовки разного уровня пишутся через `#`
```md
# H1
## H2
### H3
#### H4
##### H5
###### H6
```
Писать `####` внутри `##` не стоит, иначе визуал навигации справа будет уродливым.

### Параграф

Xerum, quo qui aut unt expliquam qui dolut labo. Aque venitatiusda cum, voluptionse latur sitiae dolessi aut parist aut dollo enim qui voluptate ma dolestendit peritin re plis aut quas inctum laceat est volestemque commosa as cus endigna tectur, offic to cor sequas etum rerum idem sintibus eiur? Quianimin porecus evelectur, cum que nis nust voloribus ratem aut omnimi, sitatur? Quiatem. Nam, omnis sum am facea corem alique molestrunt et eos evelece arcillit ut aut eos eos nus, sin conecerem erum fuga. Ri oditatquam, ad quibus unda veliamenimin cusam et facea ipsamus es exerum sitate dolores editium rerore eost, temped molorro ratiae volorro te reribus dolorer sperchicium faceata tiustia prat.

Itatur? Quiatae cullecum rem ent aut odis in re eossequodi nonsequ idebis ne sapicia is sinveli squiatum, core et que aut hariosam ex eat.

### Цитаты

Элемент blockquote представляет собой контент, цитируемый из другого источника, опционально с указанием источника, который должен быть в элементе `footer` или `cite`, а также опционально с внутренними изменениями, такими как аннотации и сокращения.

#### Цитаты без автора

> Tiam, ad mint andaepu dandae nostion secatur sequo quae.
> **Note** that you can use *Markdown syntax* within a blockquote.

#### Цитаты с автором

На однёрку можно нажать, она отправит в конец страницы со ссылками на первоисточник.

> Don't communicate by sharing memory, share memory by communicating.<br>
> — <cite>Rob Pike[^1]</cite>

[^1]: The above quote is excerpted from Rob Pike's [talk](https://www.youtube.com/watch?v=PAAkCSZUG1c) during Gopherfest, November 18, 2015.

### Таблицы

Таблицы не являются частью основной спецификации Markdown, но Hugo поддерживает их из коробки.

   Name | Age
--------|------
    Bob | 27
  Alice | 23

#### Markdown в таблицах

| Italics   | Bold     | Code   |
| --------  | -------- | ------ |
| *italics* | **bold** | `code` |

| A                                                        | B                                                                                                             | C                                                                                                                                    | D                                                 | E                                                          | F                                                                    |
|----------------------------------------------------------|---------------------------------------------------------------------------------------------------------------|--------------------------------------------------------------------------------------------------------------------------------------|---------------------------------------------------|------------------------------------------------------------|----------------------------------------------------------------------|
| Lorem ipsum dolor sit amet, consectetur adipiscing elit. | Phasellus ultricies, sapien non euismod aliquam, dui ligula tincidunt odio, at accumsan nulla sapien eget ex. | Proin eleifend dictum ipsum, non euismod ipsum pulvinar et. Vivamus sollicitudin, quam in pulvinar aliquam, metus elit pretium purus | Proin sit amet velit nec enim imperdiet vehicula. | Ut bibendum vestibulum quam, eu egestas turpis gravida nec | Sed scelerisque nec turpis vel viverra. Vivamus vitae pretium sapien |

### Блоки кода

#### Блок кода с указанием языка

```html
<!doctype html>
<html lang="en">
<head>
  <meta charset="utf-8">
  <title>Example HTML5 Document</title>
</head>
<body>
  <p>Test</p>
</body>
</html>
```

#### Блок кода с отступом в четыре пробела
```
    <!doctype html>
    <html lang="en">
    <head>
      <meta charset="utf-8">
      <title>Example HTML5 Document</title>
    </head>
    <body>
      <p>Test</p>
    </body>
    </html>
```

#### Блок кода со встроенным шорткодом Hugo
{{< highlight html >}}
<!doctype html>
<html lang="en">
<head>
  <meta charset="utf-8">
  <title>Example HTML5 Document</title>
</head>
<body>
  <p>Test</p>
</body>
</html>
{{< /highlight >}}

#### Блок кода с различиями (как в гите)

```diff
[dependencies.bevy]
git = "https://github.com/bevyengine/bevy"
rev = "11f52b8c72fc3a568e8bb4a4cd1f3eb025ac2e13"
- features = ["dynamic"]
+ features = ["jpeg", "dynamic"]
```

### Типы списков

#### Упорядоченный список

1. First item
2. Second item
3. Third item

#### Неупорядоченный список

* List item
* Another item
* And another item

#### Вложенный список

* Fruit
  * Apple
  * Orange
  * Banana
* Dairy
  * Milk
  * Cheese

### Остальные элементы — abbr, sub, sup, kbd, mark

<abbr title="Graphics Interchange Format">GIF</abbr> is a bitmap image format.

H<sub>2</sub>O

X<sup>n</sup> + Y<sup>n</sup> = Z<sup>n</sup>

Press <kbd>CTRL</kbd> + <kbd>ALT</kbd> + <kbd>Delete</kbd> to end the session.

Most <mark>salamanders</mark> are nocturnal, and hunt for insects, worms, and other small creatures.

### Hyperlinked image

[![Google](https://www.google.com/images/branding/googlelogo/1x/googlelogo_light_color_272x92dp.png)](https://google.com)

## Галерея изображений

Можно делать галерею изображений. По ним можно нажать и листать. Для примера приложил 4 изображения, которые сгенерировал ChatGPT по просьбе создать логотип для Discord канала. В данном примере три изображения сверху и одно снизу, но при пролистывании они будут в одном цикле прокрутки.

![Logo 1](logo4.jpg) ![Logo 2](logo2.jpg)![Logo 3](logo3.jpg)

![Logo 4](logo.jpg)

## Поддержка эмодзи

Эмодзи можно включить в Hugo несколькими способами
<!--more-->
Функцию [`emojify`](https://gohugo.io/functions/emojify/) можно вызывать напрямую в шаблонах или через [Inline Shortcodes](https://gohugo.io/templates/shortcode-templates/#inline-shortcodes). 

Чтобы включить emoji глобально, установите `enableEmoji: true` в [конфиге сайта](https://gohugo.io/getting-started/configuration/), после чего вы сможете использовать сокращенные коды emoji непосредственно в файлах контента;

<p><span class="nowrap"><span class="emojify">🙈</span> <code>:see_no_evil:</code></span>  <span class="nowrap"><span class="emojify">🙉</span> <code>:hear_no_evil:</code></span>  <span class="nowrap"><span class="emojify">🙊</span> <code>:speak_no_evil:</code></span></p>

[Emoji cheat sheet](http://www.emoji-cheat-sheet.com/) - полезный справочник для сокращенных кодов emoji.

***

**Примечание** Вышеуказанные шаги позволяют использовать стандартные символы и последовательности emoji Unicode в Hugo, однако отображение этих символов зависит от браузера и платформы. Для стилизации emoji вы можете использовать сторонний шрифт emoji или стек шрифтов, например:

{{< highlight html >}}
.emoji {
  font-family: Apple Color Emoji, Segoe UI Emoji, NotoColorEmoji, Segoe UI Symbol, Android Emoji, EmojiSymbols;
}
{{< /highlight >}}

{{< css.inline >}}
<style>
.emojify {
	font-family: Apple Color Emoji, Segoe UI Emoji, NotoColorEmoji, Segoe UI Symbol, Android Emoji, EmojiSymbols;
	font-size: 2rem;
	vertical-align: middle;
}
@media screen and (max-width:650px) {
  .nowrap {
    display: block;
    margin: 25px 0;
  }
}
</style>
{{< /css.inline >}}


## Математические формулы

Математическую запись в Hugo можно добавить при помощи сторонних JavaScript библиотек.

В этом примере мы будем использовать [KaTeX](https://katex.org/)

- Создать шаблон `/layouts/partials/math.html`
- В этом шаблоне используется [Auto-render Extension](https://katex.org/docs/autorender.html), но можно хостить этот скрипт локально.
- Вставить это в шаблон:  

```bash
{{ if or .Params.math .Site.Params.math }}
{{ partial "math.html" . }}
{{ end }}
```

- Для включения KaTeX глобально, надо указать `math: true` в конфиге проекта.
- Для включения KaTeX отдельно на каждой странице, надо указать `math: true` в начало файла.

**Примечание:** Используйте онлайн-справочник [поддерживаемых функций TeX](https://katex.org/docs/supported.html)


{{< math.inline >}}
{{ if or .Page.Params.math .Site.Params.math }}
<!-- KaTeX -->
<link rel="stylesheet" href="https://cdn.jsdelivr.net/npm/katex@0.16.9/dist/katex.min.css" integrity="sha384-n8MVd4RsNIU0tAv4ct0nTaAbDJwPJzDEaqSD1odI+WdtXRGWt2kTvGFasHpSy3SV" crossorigin="anonymous">
<script defer src="https://cdn.jsdelivr.net/npm/katex@0.16.9/dist/katex.min.js" integrity="sha384-XjKyOOlGwcjNTAIQHIpgOno0Hl1YQqzUOEleOLALmuqehneUG+vnGctmUb0ZY0l8" crossorigin="anonymous"></script>
<script defer src="https://cdn.jsdelivr.net/npm/katex@0.16.9/dist/contrib/auto-render.min.js" integrity="sha384-+VBxd3r6XgURycqtZ117nYw44OOcIax56Z4dCRWbxyPt0Koah1uHoK0o4+/RRE05" crossorigin="anonymous" onload="renderMathInElement(document.body);"></script>
{{ end }}
{{</ math.inline >}}

### Пример

Математические выражения в строке: $\varphi = \dfrac{1+\sqrt5}{2}= 1.6180339887…$

Математические выражения в блоке:
$$
 \varphi = 1+\frac{1} {1+\frac{1} {1+\frac{1} {1+\cdots} } } 
$$


## Hugo Shortcodes

Hugo поставляется с несколькими [встроенными шорткодами](https://gohugo.io/content-management/shortcodes/#use-hugo-s-built-in-shortcodes) для разнообразного контента, а также с [конфигурацией приватности](https://gohugo.io/about/privacy/) и набором простых шорткодов, которые обеспечивают статические и версии без JavaScript для различных встроенных элементов социальных сетей. Часть примеров можно увидеть ниже:

### YouTube Privacy Enhanced Shortcode

{{< youtube ZJthWmvUzzc >}}

<br>

---

### Twitter Simple Shortcode

{{< twitter_simple user="DesignReviewed" id="1085870671291310081" >}}

<br>

---

### Vimeo Simple Shortcode

{{< vimeo_simple 48912912 >}}

### bilibilibi Shortcode

{{< bilibili av498363026 >}}

### Gist Shortcode

{{< gist spf13 7896402 >}}

### Gitlab Snippets Shortcode

{{< gitlab 2349278 >}}

### Quote Shortcode

Stack adds a `quote` shortcode.  For example:

{{< quote author="A famous person" source="The book they wrote" url="https://en.wikipedia.org/wiki/Book">}}
Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur. Excepteur sint occaecat cupidatat non proident, sunt in culpa qui officia deserunt mollit anim id est laborum.
{{< /quote >}}

{{< quote source="Anonymous book" url="https://en.wikipedia.org/wiki/Book">}}
Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur. Excepteur sint occaecat cupidatat non proident, sunt in culpa qui officia deserunt mollit anim id est laborum.
{{< /quote >}}

{{< quote source="Some book">}}
Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur. Excepteur sint occaecat cupidatat non proident, sunt in culpa qui officia deserunt mollit anim id est laborum.
{{< /quote >}}

{{< quote author="Somebody">}}
Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur. Excepteur sint occaecat cupidatat non proident, sunt in culpa qui officia deserunt mollit anim id est laborum.
{{< /quote >}}

## Приложить ссылки в конце статьи

Чтоб использовать эту функцию, надо добавить `links` в верхнюю часть файла `.md`, где находятся настройки страницы.

На этой странице оно выглядит так:

```yaml
links:
  - title: Boosty
    description: Поддержать меня на Boosty
    website: https://boosty.to/buliway
    image: /boosty.png
```

Поле `image` может содержать как ссылку на онлайн изображение, так и на локальный файл. Если какое-то изображение используется в разных постах и его не хочется дублировать в каталог каждого отдельного поста, то можно поместить картинку в каталог `static` и вызываеть её, начиная символом `/`, что я и сделал. Если бы изображение `boosty.png` было в каталог поста, то я бы написал просто `boosty.png`, без `/` в начале пути.
