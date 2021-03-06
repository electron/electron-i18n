# Soporte para Modo Oscuro macOS

En macOS 10.14 Mojave, Apple introdujo un nuevo modo oscuro [para todo el sistema](https://developer.apple.com/design/human-interface-guidelines/macos/visual-design/dark-mode/) en sus ordenadores macOS.  Si tu aplicación Electron tiene un modo oscuro, puedes hacer que siga el modo oscuro del sistema usando [the `nativeTheme` api](../api/native-theme.md).

En macOS 10.15 Catalina, Apple introdujo una nueva opción de modo oscuro "automático" para todas las computadoras macOS. Para que las APIs `nativeTheme.shouldUseDarkColors` y `Tray` trabajen correctamente en este modo en Catalina, necesitas o bien tener `NSRequiresAquaSystemAppearance` establecido a `false` en tu archivo `Info.plist`, o estar en Electron `>=7.0.0`. Both [Electron Packager][electron-packager] and [Electron Forge][electron-forge] have a [`darwinDarkModeSupport` option][packager-darwindarkmode-api] to automate the `Info.plist` changes during app build time.

## Actualizando automáticamente las interfaces nativas

"Native Interfaces" include the file picker, window border, dialogs, context menus and more; basically, anything where the UI comes from macOS and not your app. As of Electron 7.0.0, the default behavior is to opt in to this automatic theming from the OS. Si deseas optar no participar y estás usando Electron &gt; 8.0.0, debes establecer la llave `NSRequiresAquaSystemAppearance` en el archivo `Info.plist` a `true`. Por favor tenga en cuenta que Electron 8.0.0 y superiores no permitirán que salgas de esta temática, debido al uso del SDK de macOS 10.14.

## Actualizando automáticamente tus propias interfaces

Si tu aplicación tiene su propio modo oscuro deberías activarlo y deshabilitar la sincronización con la configuración de modo oscuro del sistema. Puede hacer esto escuchando por el evento theme updated en el `systemPreferences` del modulo de Electron.

Por ejemplo:

```javascript
const { nativeTheme } = require('electron')

nativeTheme.on('updated', function theThemeHasChanged () {
  updateMyAppTheme(nativeTheme.shouldUseDarkColors)
})
```

[electron-forge]: https://www.electronforge.io/
[electron-packager]: https://github.com/electron/electron-packager
[packager-darwindarkmode-api]: https://electron.github.io/electron-packager/master/interfaces/electronpackager.options.html#darwindarkmodesupport
