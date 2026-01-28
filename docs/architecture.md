# SVG Editor Pro — Архитектура

## Стек технологий
- **HTML5** — структура
- **CSS3** — стилизация (CSS Variables, Flexbox, Grid)
- **JavaScript (ES6+)** — логика (DOM API, FileReader, Canvas, Clipboard API)
- **Google Fonts** — шрифт Inter

## Структура HTML
```
.svg-editor
├── .svg-editor__header         # Логотип и заголовок
├── .svg-editor__upload         # Зона загрузки (drag & drop)
├── .svg-editor__main           # Основная область
│   ├── .svg-editor__preview    # Превью SVG
│   └── .svg-editor__sidebar    # Панель инструментов
│       ├── Transform panel     # Поворот, отражение
│       ├── Stroke panel        # Толщина обводки
│       ├── Color panel         # Цвет, градиенты, палитра
│       └── ViewBox panel       # Редактирование viewBox
├── .svg-editor__export         # Кнопки экспорта
├── .svg-editor__toast          # Уведомления
└── .svg-editor__modal          # Модальные окна
```

## Состояние приложения (State)
```javascript
let originalSvg = null;      // Оригинальный SVG код
let currentSvg = null;       // Текущий (модифицированный) SVG
let currentFilename = '';    // Имя файла
let selectedElement = null;  // Выбранный элемент SVG
let colorMode = 'fill';      // fill | stroke | both | all
let colorType = 'solid';     // solid | gradient
let gradientType = 'linear'; // linear | radial
let rotation = 0;            // Угол поворота (0, 90, 180, 270)
let flipH = false;           // Горизонтальное отражение
let flipV = false;           // Вертикальное отражение
```

## Ключевые функции
| Функция | Описание |
|---------|----------|
| `loadFile(file)` | Загрузка SVG файла через FileReader |
| `renderSvg()` | Применение всех трансформаций и рендер |
| `applyColor(svg)` | Применение цвета/градиента к элементам |
| `applyStrokeWidth(svg)` | Изменение толщины обводки |
| `applyTransforms(svg)` | Применение поворота и отражения |
| `setupElementSelection()` | Настройка кликов по элементам |
| `showToast(text)` | Показ уведомления |
| `showModal(title, content)` | Показ модального окна |
| `downloadBlob(blob, filename)` | Скачивание файла |

## CSS Variables
```css
--sr-primary: #2563eb;        /* Основной синий */
--sr-primary-light: #3b82f6;  /* Светлый синий */
--sr-primary-lighter: #eff6ff; /* Очень светлый синий */
--sr-gray-50 to --sr-gray-900; /* Шкала серого */
--sr-border-radius: 10px;     /* Скругление */
--sr-shadow-*: ...;           /* Тени */
```

## BEM-нотация
Все классы используют префикс `svg-editor__`:
- Блок: `.svg-editor`
- Элемент: `.svg-editor__panel`
- Модификатор: `.svg-editor__btn--primary`
