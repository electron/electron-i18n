---
title: 'Проект Недели: WebTorrent'
author:
  - феросс
  - zeke
date: '2017-03-14'
---

На этой неделе мы захватили [@feross](https://github.com/feross) и [@dcposch](https://github.com/dcposch) , чтобы поговорить о WebTorrent, работающий на web-сайте торрент-клиент, который соединяет пользователей с целью формирования распределенной, децентрализованной сети между браузером и браузером.

---

## Что такое WebTorrent?

[WebTorrent](https://webtorrent.io) является первым торрент-клиентом, который работает в браузере. Полностью написан в JavaScript и может использовать WebRTC для peer-to-peer транспорта. Нет плагина для браузера, расширения или установки.

Используя открытые веб-стандарты, WebTorrent связывает пользователей с целью создания распределенной децентрализованной сети с браузером для эффективной передачи файлов.

Демонстрацию WebTorrent вы можете увидеть здесь: [webtorrent.io](https://webtorrent.io/).

<a href="https://webtorrent.io/">
  <img alt="домашняя страница веб-торрента" src="https://cloud.githubusercontent.com/assets/2289/23912149/1543d2ce-089c-11e7-8519-613740c82b47.jpg">
</a>

## Почему это круто?

Представьте себе видео-сайт, как YouTube, но где посетители помогают размещать контент сайта. Чем больше людей используют WebTorrent, тем быстрее и устойчивее он становится.

Браузер вырезает посредника и позволяет людям общаться на своих собственных условиях. Больше нет клиента/сервера – просто сеть соседей, все равно. WebTorrent является первым шагом в пути к перераспределению Интернета.

## Где Electron попадает на картину?

Около года назад мы решили построить [WebTorrent Desktop](https://webtorrent.io/desktop/), версию WebTorrent, которая работает как настольное приложение.

[![Окно WebTorrent Desktop player](https://cloud.githubusercontent.com/assets/2289/23912152/154aef0a-089c-11e7-8544-869b0cd642b1.jpg)](https://webtorrent.io/desktop/)

Мы создали WebTorrent Desktop по трем причинам:

1. Нам хотелось чистого, легкого и свободного от рекламы торрента с открытым исходным кодом
2. Мы хотели, чтобы торрент-приложение с хорошей поддержкой стриминга
3. Нам нужен "гибридный клиент", который соединяет сети BitTorrent и WebTorrent

## Если мы уже можем скачать торренты в моем браузере, почему приложение для рабочего стола?

Во-первых, немного фона на дизайне WebTorrent.

<a href="https://webtorrent.io/desktop/">
  <img alt="логотип веб-торрента" src="https://cloud.githubusercontent.com/assets/2289/23912151/154657e2-089c-11e7-9889-6914ce71ebc9.png" width="200" align="right">
</a>

В первые дни BitTorrent в качестве транспортного протокола использовал TCP. Позднее uTP соответствовал многообещающей производительности и дополнительным преимуществам над TCP. Каждый основной клиент торрентов в конечном итоге адаптирован uTP, и сегодня вы можете использовать BitTorrent по любому протоколу. Следующим логическим шагом является протокол WebRTC . Это дает обещание совместимости с веб-браузерами – одна гигантская P2P сеть, состоящая из всех настольных клиентов BitTorrent и миллионов веб-браузеров.

«Веб пиры» (торрент-соседи, которые запускаются в веб-браузере) делают сеть BitTorrent более прочной, добавив миллионы новых пиров, и распространения BitTorrent на десятки новых вариантов использования. WebTorrent следует спецификации BitTorrent как можно ближе, чтобы существующие клиенты BitTorrent могли легко добавить поддержку WebTorrent.

Некоторые торрент-приложения, такие как [Vuze](https://www.vuze.com/) уже поддерживают веб-узлы, но мы не хотим ждать пока остальные, чтобы добавить поддержку. **По сути, WebTorrent Desktop - это наш способ ускорить принятие WebTorrent протокола.** Создавая отличное торрент-приложение, которое люди действительно хотят использовать, мы увеличиваем количество соседей в сети, которые могут делиться торрентами с веб-пиров (i. . пользователей на сайтах).

## Каковы некоторые интересные варианты использования торрентов сверх того, что люди уже знают, что они могут делать?

Одним из наиболее интересных способов использования WebTorrent является доставка с помощью сверстников. Некоммерческие проекты, такие как [Википедия](https://www.wikipedia.org/) и [Интернет-архив](https://archive.org/) могут снизить пропускную способность и стоимость хостинга, предоставляя посетителям чип. Популярный контент может быть предоставлен браузером для браузера, быстро и дешево. Контент с редким доступом может быть предоставлен надёжно через HTTP от исходного сервера.

Интернет архив уже обновил свои торрент-файлы, так что они отлично работают с WebTorrent. Так что если вы хотите встроить Интернет-архив на ваш сайт, вы можете сделать это таким образом, чтобы уменьшить хостинг для архива, позволяет им тратить больше денег на фактическое архивирование Интернета!

Есть также интересные варианты бизнес-использования, от CDN до доставки приложений через P2P.

## Каковы некоторые из ваших любимых проектов, использующих WebTorrent?

![скриншот приложения gaia](https://cloud.githubusercontent.com/assets/2289/23912148/154392c8-089c-11e7-88a8-3d4bcb1d2a94.jpg)

Самая крутая вещь, построенная с помощью WebTorrent, заканчивается, вероятно, [3D Star Map Gaia](http://charliehoey.com/threejs-demos/gaia_dr1.html). Это маленькая трехмерная интерактивная симуляция Млечного Пути. Данные загружаются из торрента прямо в вашем браузере. Мы вдохновляемся пролетать через нашу звездную систему и понимаем, насколько мало мы людей по сравнению с громадой нашей вселенной.

Вы можете прочитать о том, как это было сделано в [Torrenting The Galaxy](https://medium.com/@flimshaw/torrenting-the-galaxy-extracting-2-million-3d-stars-from-180gb-of-csvs-457ff70c0f93), пост в блоге, где автор, Чарли Хоэйй, объясняет, как он создал звезду с помощью WebGL и WebTorrent.

<a href="https://brave.com/">
  <img alt="храбрый логотип" src="https://cloud.githubusercontent.com/assets/2289/23912147/1542ad4a-089c-11e7-8106-15c8e34298a9.png" width="150" align="left">
</a>

Мы также являемся огромными фанатами [Храбрый](https://brave.com/). Brave - это браузер, автоматически блокирующий рекламу и трекеры, чтобы сделать интернет быстрее и безопаснее. Brave недавно добавила поддержку торрентов, так что вы можете [просматривать традиционные торренты без использования отдельного приложения](https://torrentfreak.com/brave-a-privacy-focused-browser-with-built-in-torrent-streaming-170219/). Эта функция основана на WebTorrent.

Так же, как и большинство браузеров могут рендерить PDF-файлы, Brave может рендерить magnet ссылки и торрент-файлы. Это просто другой тип контента, который изначально поддерживает браузер.

Один из соучредителей Brave - на самом деле Брендан Айх, создатель JavaScript, язык, в котором мы написали WebTorrent, поэтому мы считаем, что это довольно круто, что Brave выбрал для интеграции WebTorrent.

## Почему вы выбрали создание WebTorrent Desktop на Electron?

<a href="https://webtorrent.io/desktop/">
  <img alt="Окно WebTorrent Desktop" src="https://cloud.githubusercontent.com/assets/2289/23912150/15444542-089c-11e7-91ab-7fe3f1e5ee43.jpg" align="right" width="450">
</a>

Есть мема, что приложения Electron "bloated", потому что они включают весь модуль контента Chrome в каждом приложении. В некоторых случаях это частично верно (инсталлятор приложения Electron обычно ~40MB, где установщик приложений для ОС обычно ~20MB).

Однако, в случае рабочего стола WebTorrent, мы используем почти все функции Electron, а также многие десятки функций Chrome в процессе нормальной работы. Если мы хотим реализовать эти функции с нуля для каждой платформы, было бы несколько месяцев или лет спустя для создания нашего приложения, или мы смогли бы выпустить только одну платформу.

Просто чтобы получить идею, мы используем [док-интеграцию Electron](https://electronjs.org/docs/api/app/#appdockbouncetype-macos) (чтобы показать прогресс загрузки), интеграция строки меню [](https://electronjs.org/docs/api/menu) (для запуска в фоновом режиме), [обработчик протокола](https://electronjs.org/docs/api/app/#appsetasdefaultprotocolclientprotocol-path-args-macos-windows) (для открытия magnet-ссылок), [экономить энергопотребление](https://electronjs.org/docs/api/power-save-blocker/) (для предотвращения сна во время воспроизведения видео), и [автоматическое обновление](https://electronjs.org/docs/api/auto-updater). Что касается функций Chrome, то мы используем тег `<video>` (для воспроизведения различных форматов видео), тег `<track>` (для поддержки закрытых подписей), drag-and-drop support и WebRTC (который не является тривиальным для использования в собственном приложении).

Не говоря уже о том, что наш движок торрентов написан на JavaScript и предполагает, что существует множество Node API, но особенно `require('net')` and `require('dgram')` для поддержки TCP и UDP сокетов.

По сути, Electron - это то, что нам нужно, и у нас был полный набор функций, необходимых для доставки надежного и отполированного приложения в рекордное время.

## Каковы ваши любимые вещи в Electron?

Библиотека WebTorrent находится в разработке в течение двух лет как сторонний проект с открытым исходным кодом. **Мы создали WebTorrent Desktop через четыре недели.** Electron является основной причиной, по которой мы смогли быстро создать и отправить наше приложение.

Точно так же как узел. , сделав серверное программирование доступным для поколения jQuery-используя фронт-энд, Electron делает разработку родного приложения доступной для всех, кто знаком с Web или Node. с разработкой. Электрон чрезвычайно расширяет свои возможности.

## Есть ли код общего доступа для веб-сайта и клиента рабочего стола?

Да, [`webtorrent` npm пакет](https://npmjs.com/package/webtorrent) работает в Node.js, в браузере и в Electron. Точный код может быть запущен во всех средах – это красота JavaScript. Это сегодня универсальное время исполнения. Апплеты Java обещали "писать однажды, запускать везде", но это видение не было воплощено в реальности по ряду причин. Electron, больше, чем любая другая платформа, фактически очень темная близка к идеалу.

## Каковы некоторые вызовы, с которыми вы столкнулись при создании WebTorrent?

В ранних версиях приложения мы пытались сделать пользовательский интерфейс. Мы помещаем торрент-движок в тот же процесс рендерера, который рисует главное окно приложения, которое предсказуемо приводило к замедлению в любое время интенсивной работы процессора от торрент-движка (например, проверка торрентных штук, полученных от пиров).

Мы исправили это, переместив торрент-движок на второй, невидимый процесс визуализации, который мы общаемся более чем с [IPC](https://electronjs.org/docs/api/ipc-main/). Таким образом, если этот процесс вкратце использует много процессоров, пользовательский интерфейс не будет затронут. Гладкая маслопрокрутка и анимация настолько удовлетворительны.

Примечание: мы должны были поместить торрент-движок в процесс визуализации, вместо "основного" процесса, потому что нам нужен доступ к WebRTC (который доступен только в устройстве.)

## В каких областях Electron следует улучшить?

Мы хотели бы увидеть лучшую документацию по созданию и отправке готовых приложений, особенно вокруг таких сложных вопросов, как подписание кода и автоматическое обновление. Нам пришлось узнать о лучших практиках, отправившись в исходный код и попросив в Twitter!

## Сделано ли WebTorrent Desktop? Если нет, что будет дальше?

Мы считаем, что текущая версия WebTorrent Desktop отлична, но всегда есть возможность улучшения. В настоящее время мы работаем над улучшением полирования, производительности, поддержки субтитров и поддержки видео кодеков.

Если вы заинтересованы в участии в проекте, посетите [нашу страницу GitHub](https://github.com/feross/webtorrent-desktop)!

## Любые советы по разработке Electron, которые могут быть полезны другим разработчикам?

[Feross](http://feross.org/), один из разработчиков WebTorrent Desktop, недавно прочитал разговор *"Real world Electron: Building Cross-platform desktop apps with JavaScript"* на NodeConf Argentina , который содержит полезные советы по выпуску приложения Electron с полированным приложением. Обсуждение особенно полезно, если вы находитесь на этапе, где у вас есть базовое рабочее приложение, и вы пытаетесь перейти к следующему уровню польского и профессионализма.

[Смотреть здесь](https://www.youtube.com/watch?v=YLExGgEnbFY): <iframe width="100%" height="360" src="https://www.youtube.com/embed/YLExGgEnbFY?rel=0" frameborder="0" allowfullscreen mark="crwd-mark"></iframe>

[Слайды здесь](https://speakerdeck.com/feross/real-world-electron):

<script async class="speakerdeck-embed" data-id="5aae08bb7c5b4dbd89060cff11bb1300" data-ratio="1.77777777777778" src="//speakerdeck.com/assets/embed.js"></script>

[DC](https://dcpos.ch/), другой участник WebTorrent, написал [контрольный список вещей, которые вы можете](https://blog.dcpos.ch/how-to-make-your-electron-app-sexy) сделать, чтобы ваше приложение чувствовало себя полированным и родным. Он содержит кодовые примеры и охватывает такие вещи, как интеграция с macOS, перетаскивание и удаление уведомлений, настольные уведомления и обеспечение быстрой загрузки вашего приложения.

