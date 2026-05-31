<div align="right">

[English](README.md) · [中文](README-zh.md) · [日本語](README-ja.md) · [한국어](README-ko.md) · Русский

</div>

# general-readme-skill

> Генерация профессиональных README файлов для любого проекта с помощью AI-ассистентов

![Markdown](https://img.shields.io/badge/Markdown-000000?style=flat&logo=markdown&logoColor=white)
![Claude Code](https://img.shields.io/badge/Claude_Code-D97757?style=flat&logo=claude&logoColor=white)
![Zero Dependencies](https://img.shields.io/badge/Dependencies-0-blue?style=flat)

## Возможности

| Возможность | Описание |
|---|---|
| Множество стилей | Три профиля написания: энергичный, минималистичный и профессиональный |
| Система бейджей | Автоматическая генерация бейджей shields.io в трёх визуальных стилях |
| Многоязычность | Генерация README на английском, китайском, японском, корейском, русском и других языках |
| Нулевые зависимости | Не требует внешних CLI, рантаймов или сетевых сервисов |
| Кроссплатформенность | Работает с Claude Code, GitHub Copilot и Cursor |
| Приватность | Автоматическая маскировка чувствительных ключей, паролей и личной информации |

## Быстрый старт

### Claude Code

```bash
mkdir -p .claude/skills/general-readme
cp SKILL.md .claude/skills/general-readme/
cp -r references/ .claude/skills/general-readme/
```

### GitHub Copilot

```bash
mkdir -p .github
cp SKILL.md .github/copilot-instructions.md
cp -r references/ .github/copilot-instructions/references/
```

### Cursor

```bash
mkdir -p .cursor/rules
cp SKILL.md .cursor/rules/general-readme.mdc
cp -r references/ .cursor/rules/references/
```

## Использование

Введите `/readme` или скажите "generate readme" в вашем AI-ассистенте. Навык проведёт вас через:

1. **Конфигурация** — Выбор стиля написания, бейджей и языков
2. **Сканирование проекта** — Автоматическое определение типа проекта, технологического стека и структуры
3. **Генерация** — Создание README по структуре «перевёрнутой пирамиды»
4. **Вывод** — Генерация основного файла и переводов

### Поддерживаемые команды

| Команда | Описание |
|---|---|
| `/readme` | Запуск генерации README |
| `generate readme` | Триггер на естественном языке |
| `write readme` | Триггер на естественном языке |
| `帮我写 README` | Триггер на китайском языке |
| `更新README` | Обновление существующего README |

## Структура проекта

```
general-readme-skill/
├── SKILL.md                # Основной файл определения навыка
├── examples/               # Примеры README файлов
│   ├── app-readme.md       # Пример полноценного приложения
│   ├── cli-readme.md       # Пример CLI инструмента
│   └── library-readme.md   # Пример библиотеки/пакета
├── install/                # Руководства по установке
│   ├── claude-code.md      # Настройка Claude Code
│   ├── copilot.md          # Настройка GitHub Copilot
│   └── cursor.md           # Настройка Cursor
└── references/             # Справочные файлы
    ├── badges.md           # Маппинг технологий на бейджи
    ├── badge-styles.md     # Правила布局 бейджей
    ├── diagram-templates.md # Шаблоны Mermaid/SVG
    ├── language-guide.md   # Правила многоязычности
    ├── section-guidelines.md # Правила написания секций
    └── tone-profiles.md    # Определения стилей написания
```

## Технологический стек

### Документация

| Технология | Назначение |
|---|---|
| Markdown | Основной формат контента |
| shields.io | Генерация бейджей |
| Mermaid | Диаграммы архитектуры |

### Поддерживаемые платформы

| Платформа | Метод интеграции |
|---|---|
| Claude Code | Директория `.claude/skills/` |
| GitHub Copilot | `.github/copilot-instructions.md` |
| Cursor | Директория `.cursor/rules/` |

## Участие в разработке

1. Форкните репозиторий
2. Создайте ветку для функции (`git checkout -b feature/amazing`)
3. Закоммитьте изменения (`git commit -m 'feat: add amazing feature'`)
4. Запушьте в ветку (`git push origin feature/amazing`)
5. Откройте Pull Request

## Лицензия

Файл LICENSE не обнаружен. Добавьте LICENSE для уточнения лицензирования проекта.
