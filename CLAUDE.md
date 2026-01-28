# SVG Editor Pro

## Описание проекта
Веб-инструмент для редактирования, перекраски и экспорта SVG-файлов. Работает полностью в браузере без серверной части.

## Технологии
- Чистый HTML/CSS/JavaScript (без зависимостей)
- Шрифт Inter (Google Fonts)
- Современный CSS с CSS Variables

## Структура проекта
```
svg-editor/
├── change-color-svg.html  # Основной файл приложения
├── CLAUDE.md              # Инструкции для Claude
└── docs/
    ├── project_status.md  # Статус и план разработки
    ├── changelog.md       # История изменений
    └── architecture.md    # Архитектура проекта
```

## Правила разработки
1. Весь код в одном HTML-файле (inline CSS и JS)
2. Поддержка мобильных устройств (responsive)
3. Современный дизайн в светлых тонах
4. BEM-нотация для CSS классов (префикс `svg-editor__`)
5. После каждой фичи — коммит и пуш

## После выполнения задачи
После каждой задачи обновлять:
- `docs/project_status.md` — отметить выполненные задачи
- `docs/changelog.md` — добавить запись о изменениях

## Git
- Remote: git@github.com:Postnov/svg-editor.git
- Branch: main
