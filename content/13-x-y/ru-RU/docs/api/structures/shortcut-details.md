# Объект ShortcutDetails

* `target` String - цель запуска из этого ярлыка.
* `cwd` String (опционально) - Рабочий каталог. По умолчанию пусто.
* `args` String (опционально) - Аргументы, которые будут применены к `target`, когда запускается из этого ярлыка. По умолчанию пусто.
* `description` String (опционально) - Описание ярлыка. По умолчанию пусто.
* `icon` String (опционально) - Путь к значку, может быть DLL или EXE. `icon` и `iconIndex` должны быть установлены вместе. По умолчанию пусто, будет использоваться значок цели.
* `iconIndex` Number (опционально) - Идентификатор ресурса иконки, когда `icon` берется из DLL или EXE. По умолчанию 0.
* `appUserModelId` String (опционально) - Идентификатор пользовательской модели приложения. По умолчанию пусто.
* `toastActivatorClsid` String (optional) - The Application Toast Activator CLSID. Needed for participating in Action Center.
