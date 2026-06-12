# Как добавить свою тему

Любой желающий может опубликовать тему в маркетплейсе Tema. Это бесплатно и не требует специальных знаний — достаточно уметь редактировать JSON.

---

## Быстрый старт — через приложение Tema

Самый простой способ — создать тему прямо в Tema и воспользоваться встроенной функцией публикации:

1. Открой **Редактор тем** → настрой цвета, добавь обои
2. Нажми **Сохранить в Мои темы**
3. Перейди в **Мои темы** → кнопка **Опубликовать**
4. Выбери тему → нажми **Скопировать JSON** → **Открыть GitHub →**
5. Вставь JSON в открывшийся issue — мейнтейнер проверит и добавит в каталог

---

## Структура папки темы

```
your-theme-id/
  theme.json           ← обязательно
  preview.png          ← обязательно  (рекомендуется 400×250 px)
  wallpaper.png        ← опционально  (будет установлен как обои рабочего стола)
  screenshots/         ← опционально  (слайдер на странице профиля)
    1.png
    2.png
    3.png
  cursors/             ← опционально  (файлы курсоров .cur / .ani)
    arrow.cur
    hand.cur
    ibeam.cur
    wait.cur
    ...
  icons/               ← опционально  (иконки папок .ico)
    folder.ico
```

### Screenshots

Скриншоты отображаются в слайдере на странице профиля темы. Добавь поле в `theme.json`:

```json
"screenshots": ["1.png", "2.png", "3.png"]
```

Рекомендуемый размер: **1920×1080 px**, формат PNG или JPG.

---

## Формат theme.json

```json
{
  "id": "your-theme-id",
  "name": "Название темы",
  "version": "1.0.0",
  "author": "твой-github-ник",
  "description": "Одно предложение о теме.",
  "preview": "preview.png",
  "wallpaper": "wallpaper.png",
  "accentColor": "#818cf8",

  "darkMode": true,
  "transparency": true,
  "colorOnTitleBars": true,
  "hasCursors": false,

  "folderIcons": {
    "enabled": false,
    "iconPath": "icons/folder.ico"
  },

  "colors": {
    "accent":     "#818cf8",
    "background": "#0d0d2b",
    "surface":    "#1a1a40",
    "text":       "#e0e0f0"
  },

  "animations": {
    "windowOpen":     "spring",
    "windowClose":    "fade",
    "minimize":       "spring",
    "taskbarHover":   "glow",
    "menuTransition": "fade",
    "tooltipFade":    true
  },

  "widgets": [],
  "tags": ["dark", "minimal"],
  "createdAt": "2026-01-01"
}
```

### Поля оформления системы

| Поле | Тип | Описание |
|---|---|---|
| `darkMode` | `boolean` | Включить тёмный режим Windows |
| `transparency` | `boolean` | Прозрачность окон (эффект Mica/Acrylic) |
| `colorOnTitleBars` | `boolean` | Цветные заголовки окон |
| `hasCursors` | `boolean` | Есть ли папка `cursors/` с курсорами |

### Допустимые значения анимаций

| Поле | Значения |
|---|---|
| `windowOpen` / `windowClose` / `minimize` | `"spring"` `"fade"` `"slide"` `"none"` |
| `taskbarHover` | `"glow"` `"scale"` `"none"` |
| `menuTransition` | `"fade"` `"slide"` `"none"` |

### Рекомендуемые теги

`dark` `light` `minimal` `colorful` `purple` `blue` `pink` `green` `warm` `cool`
`space` `nature` `hacker` `clean` `gradient` `grey` `yellow` `red`

---

## Курсоры

Если в теме есть курсоры, создай папку `cursors/` и положи туда `.cur` или `.ani` файлы.
Поддерживаемые имена файлов:

| Файл | Курсор |
|---|---|
| `arrow.cur` | Обычный указатель |
| `hand.cur` | Ссылка / рука |
| `ibeam.cur` | Текстовый курсор |
| `wait.cur` | Загрузка (часы) |
| `crosshair.cur` | Прицел |
| `sizeall.cur` | Перемещение |
| `sizens.cur` | Изменение размера ↕ |
| `sizewe.cur` | Изменение размера ↔ |
| `sizenwse.cur` | Изменение размера ↘ |
| `sizenesw.cur` | Изменение размера ↙ |
| `no.cur` | Запрещено |
| `help.cur` | Справка |

Не обязательно добавлять все — приложение применит только те, что есть.

---

## Как отправить тему

1. **Форкни** этот репозиторий
2. Создай папку `your-theme-id/` с `theme.json` и `preview.png`
3. Добавь запись о теме в `index.json` (сохраняй алфавитный порядок по `id`)
4. Открой **Pull Request** с кратким описанием

После того как PR будет проверен и смержен, тема появится в маркетплейсе Tema у всех пользователей.

---

## Требования

- Никакого оскорбительного или вредоносного контента
- `id` — только строчные буквы и дефисы, например `my-cool-theme`
- `accentColor` — валидный hex-цвет из 6 символов, например `#818cf8`
- `preview.png` обязателен — темы без превью не принимаются
- `version` в формате semver, например `1.0.0`
- Тема должна выглядеть завершённой: заполнены все цвета, есть описание
