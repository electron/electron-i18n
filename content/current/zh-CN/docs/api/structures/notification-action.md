# NotificationAction 对象

* `type` 类型：String - 此类操作可以作为 `按钮`.
* `text` 类型：String（可选） - 给定操作的标签。

## 平台 / 操作 支持

| 操作类型     | 平台支持  | `text` 参数    | `text` 参数默认值                                   | 局限性                                                                                                                |
| -------- | ----- | ------------ | ---------------------------------------------- | ------------------------------------------------------------------------------------------------------------------ |
| `button` | macOS | button 显示的内容 | "Show" ( 如果是第一个这类 `button`，则为系统默认的本地化字符串，否则为空) | 只使用第一个。 如果提供了多个, 则第一个之外的那些将被列为附加操作 (当鼠标停留在按钮上时显示)。 任何这类操作都与 ` hasReply ` 不兼容, 如果 ` hasReply ` 为 ` true `, 则将忽略此行为。 |

### MacOS系统上的按钮支持

为了在 macOS 上使用额外的通知按钮, 您的应用程序必须符合以下标准。

* 应用程序已签名
* 应用将`info.plist`变量中的`NSUserNotificationAlertStyle`属性值设置为`alert`

这些要求如果有一个不满足，按钮就不会显示。
