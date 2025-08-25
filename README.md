# Ресурсы для игр

В этом репозитории хранятся графические и вспомогательные ресурсы для игр: обложки, фоны, архивы с модами и метаданные. Ресурсы организованы по папкам, а описания и ссылки — в файле games_info.json.

## Что включено
- Обложки (cover) и фоны (background).
- Ссылки на файлы (gameDriveUrl, modsDriveUrl) и raw-URL для изображений.
- Версионирование и статус каждой игры.
- Поля для управления отображением в лаунчере (options_tab).

## Пример структуры репозитория
```
/resources/ или /covers/ и /backgrounds/
    ├─ covers/
    │   ├─ section.jpg
    │   └─ lethalc.jpg
    ├─ backgrounds/
    │   ├─ section.jpg
    │   └─ lethalc.jpg
games_info.json
README.md
```

## Структура файла games_info.json
Файл games_info.json содержит корневое поле version и массив games. Каждая запись описывает игру и имеет набор полей, используемых лаунчером.

Пример записи (схема соответствует текущему содержимому):
```json
{
  "version": "1",
  "games": [
    {
      "game": "Minecraft",
      "game_name": "Секция Сервер",
      "game_version": "1.0.0",
      "mods_version": "1.0.0",
      "coverRelativePath": "covers/section.jpg",
      "coverRawUrl": "https://.../covers/section.jpg",
      "bgRelativePath": "backgrounds/section.jpg",
      "bgRawUrl": "https://.../backgrounds/section.jpg",
      "gameurl": "https://drive.google.com/...",
      "modsurl": "https://drive.google.com/...",
      "status": "Active",         // "Active" или "Inactive"
      "options_tab": "Enabled"    // "Enabled" или "Disabled"
    }
  ]
}
```

Обязательные и рекомендуемые поля:
- game — короткий идентификатор.
- game_name — отображаемое имя.
- game_version, mods_version — версии для совместимости.
- coverRelativePath, bgRelativePath — пути внутри репозитория.
- coverRawUrl, bgRawUrl — прямые ссылки на файлы (raw).
- gameDriveUrl, modsDriveUrl — ссылки на архивы или страницы загрузки (может быть "[WIP]").
- status — определяет, активна ли игра в списке (Active/Inactive).
- options_tab — управляет доступностью вкладки опций (Enabled/Disabled).

## Как работать с games_info.json
- При добавлении или изменении ресурсов: обновите соответствующие RelativePath и RawUrl.
- При изменении содержимого ресурса увеличьте соответствующую версию (game_version или mods_version).
- Изменяйте status и options_tab для управления отображением игры в лаунчере.
- Поддерживайте единообразие имён и формата ссылок.

Примечание: перед массовыми изменениями делайте резервную копию games_info.json и при необходимости добавляйте контрольные суммы для автоматических обновлений.
