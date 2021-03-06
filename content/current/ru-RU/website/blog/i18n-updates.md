---
title: "Обновления интернационализации"
author: vanessayuenn
date: '2018-06-20'
---

С момента [запуска](https://electronjs.org/blog/new-website) нового интернационализированного веб-сайта Electron, мы прилагаем все усилия, чтобы сделать опыт разработки Electron еще более доступным для разработчиков вне англоязычного мира.

Так что здесь мы с некоторыми интересными обновлениями i18n!

---

## 🌐 Языковые переключатели

Знаете ли вы, что многие люди, которые читают переведенную документацию, часто перекрестно ссылаются на оригинальную английскую документацию? They do this to familiarize themselves with Russian docs, and to avoid outdated or inaccurate translations, which is one caveat of internationalized documentations.

<figure>
  <img class="screenshot" src="https://user-images.githubusercontent.com/6842965/35578586-cae629e2-05e4-11e8-9431-0278f8c2b39f.gif" alt="Переключение языка на документации Electron">
</figure>

Для упрощения перекрестной ссылки на английскую документацию, мы недавно поставили функцию, которая позволяет вам легко переключать раздел документации Electron между английским и любым языком, на котором вы просматриваете сайт. Переключатель языка будет отображаться до тех пор, пока вы не выбрали английскую локаль на сайте.

## ⚡ Быстрый доступ к странице перевода

<figure>
  <img class="screenshot" src="https://user-images.githubusercontent.com/6842965/36511386-c32e31fc-1766-11e8-8484-7466be6a5eb0.png" alt="Новый подвал документации Electron на японском языке">
  <figcaption>Подвал документации Electron на японском</figcaption>
</figure>

Обратите внимание на опечатки или неправильный перевод во время чтения документации? Вам больше не нужно авторизоваться в Crowdin, выбирайте ваш локаль, найдите файл, который вам понравился, и т.д. Вместо этого вы можете просто прокрутить вниз к нижней части этой документации, и нажмите кнопку "Перевести этот документ" (или эквивалент на вашем языке). Voila! Вы попали прямо на страницу перевода Crowdin. Примените ваш перевод магии!

## 📈 Некоторая статистика

С тех пор как мы опубликовали документацию Electron i18n, мы видели рост _огромных_ переводов членов сообщества Electron со всего мира. На сегодняшний день у нас есть **1,719,029 строк переведены, от 1,066 общинных переводчиков, и на 25 языках**.

<figure>
  <a href="https://crowdin.com/project/electron/">
    <img class="screenshot" src="https://user-images.githubusercontent.com/6842965/41649826-ca26037c-747c-11e8-9594-5ce12d2978e2.png" alt="Прогноз перевода, предоставленный Crowdin">
    <figcaption>Прогноз перевода предоставлен Crowdin</figcaption>
  </a>
</figure>

Вот забавный график, показывающий примерное количество времени, необходимого для перевода проекта на каждый язык, если сохранится существующий темп (на основе деятельности по проекту в течение последних 14 дней на момент написания).

## 📃 опрос переводчика

Мы хотели бы дать огромное ❤️ благодарим вас ❤️ всем кто поделился своим временем помочь улучшить Electron! Чтобы должным образом признать тяжелую работу нашего сообщества переводчиков, мы создали опрос, чтобы собрать некоторую информацию (а именно сопоставление имен пользователей Crowdin и Github) о наших переводчиках.

Если вы являетесь одним из наших невероятных переводчиков, пожалуйста, заполните это несколько минут: https://goo.gl/forms/b46sjdcHmlpV0GKT2.

## Интернационализация узла 🙌

Из-за успеха инициативы i18n Electron, Node.js решил моделировать [их переработанное усилие i18n](https://github.com/nodejs/i18n) после того, как мы используем и шаблон! 🎉 Узел [. s i18n инициатива](https://github.com/nodejs/i18n) была начата и приобрела большой импульс, но вы можете прочитать раннее предложение и рассуждать его [здесь](https://medium.com/the-node-js-collection/internationalizing-node-js-fe7761798b0a).

## 🔦 Руководство

Если вы заинтересованы в присоединении к нашим усилиям, чтобы Electron стал более дружелюбным на международном уровне, у нас есть dandy-dandy [руководство](https://github.com/electron/i18n/blob/master/contributing.md) , которое поможет вам начать. Счастливая интернационализация! 📚
