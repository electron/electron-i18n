# Объект ThumbarButton

* `icon` [NativeImage](../native-image.md) - иконка, отображаемая в миниатюре на панели инструментов.
* `click` Function
* `tooltip` String (опционально) - текст всплывающей подсказки на кнопке.
* `flags` String[] (опционально) - Управление конкретными состояниями и поведением кнопки. По умолчанию, является `['enabled']`.

`flags` — это массив, который может включать следующие `строки`:

* `enabled` - кнопка активна и доступна пользователю.
* `disabled` - Кнопка отключена. Она присутствует, но имеет неактивное визуальное состояние и не будет реагировать на действия пользователя.
* `dismissonclick` - когда кнопка нажата, окно миниатюры закрывается немедленно.
* `nobackground` - не рисует границы кнопок, использует только изображение.
* `hidden` - кнопка не отображается пользователю.
* `noninteractive` - Кнопка включена, но не интерактивна; ни одно состояние кнопки не отображается. Это значение предназначено для случаев, когда кнопка используется в уведомлении.
