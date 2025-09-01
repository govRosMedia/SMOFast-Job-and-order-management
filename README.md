# SMOFast: Управление заданиями и заказами

[![Version](https://img.shields.io/badge/version-2.1-blue.svg)](manifest.json)
[![License](https://img.shields.io/badge/license-MIT-green.svg)](LICENSE)
[![Manifest](https://img.shields.io/badge/manifest-v2-orange.svg)](manifest.json)

Браузерное расширение для Chrome/Firefox для управления заданиями и заказами с сайта smofast.com.

## ⚠️ Важные уведомления

- **Manifest v2 устарел** - Chrome прекращает поддержку в 2024 году
- **Требуется миграция** на Manifest v3
- **Есть проблемы безопасности** - см. [Security Audit](SECURITY_AUDIT.md)

## 📋 Возможности

- 📊 Отображение списка активных заданий
- 🚀 Управление быстрыми заказами  
- 📈 Мониторинг статуса выполнения
- 💰 Отслеживание стоимости заказов
- 🔄 Автоматическое обновление данных

## 🛠 Технологии

- **Frontend:** Vue.js 2.x, Bootstrap 3.x, jQuery
- **Build:** Webpack
- **API:** smofast.com REST API
- **Browser:** Chrome Extension API (Manifest v2)

## 📦 Установка

### Из исходного кода
1. Клонируйте репозиторий:
   ```bash
   git clone https://github.com/govRosMedia/SMOFast-Job-and-order-management.git
   ```

2. Откройте Chrome -> Расширения -> Режим разработчика

3. Нажмите "Загрузить распакованное расширение"

4. Выберите папку проекта

### Из Chrome Web Store
*Пока недоступно - требуется публикация*

## 🚀 Использование

1. Нажмите на иконку расширения в браузере
2. Авторизуйтесь на smofast.com (если требуется)
3. Просматривайте задания во вкладке "Задания"
4. Управляйте быстрыми заказами во вкладке "Быстрый заказ"

## 📊 Состояние проекта

### ✅ Что работает
- ✅ Базовый функционал отображения данных
- ✅ Интеграция с smofast.com API
- ✅ Адаптивный интерфейс
- ✅ Автоматическое обновление

### ⚠️ Известные проблемы
- ⚠️ Устаревший Manifest v2
- ⚠️ Большой размер bundle (~800KB)
- ⚠️ Отсутствует Content Security Policy
- ⚠️ Уязвимости безопасности (XSS)
- ⚠️ Неоптимизированная производительность

### 🔄 В планах
- 🔄 Миграция на Manifest v3
- 🔄 Оптимизация размера bundle
- 🔄 Добавление TypeScript
- 🔄 Обновление зависимостей
- 🔄 Исправления безопасности

## 📋 Отчеты и диагностика

- 📊 [Полный диагностический отчет](DIAGNOSTIC_REPORT.md)
- 🔒 [Аудит безопасности](SECURITY_AUDIT.md)  
- ⚡ [Анализ производительности](PERFORMANCE_ANALYSIS.md)

## 🛡️ Безопасность

**Уровень безопасности: НИЗКИЙ** ⚠️

Обнаружены критические уязвимости:
- Отсутствие CSP
- Возможность XSS атак
- HTTP разрешения
- Устаревшие зависимости

См. подробности в [Security Audit](SECURITY_AUDIT.md)

## ⚡ Производительность

**Текущая производительность: НЕУДОВЛЕТВОРИТЕЛЬНАЯ** ⚠️

Основные проблемы:
- Bundle size: ~800KB (слишком большой)
- Load time: 300-500ms (медленно)
- Memory usage: ~30MB (много)

См. подробности в [Performance Analysis](PERFORMANCE_ANALYSIS.md)

## 🔧 Разработка

### Настройка среды разработки

**❌ Текущее состояние:**
- Отсутствует `package.json`
- Нет исходных файлов (только bundle)
- Отсутствуют конфигурации сборки

**✅ Рекомендуемая настройка:**

1. Восстановить исходный код:
   ```bash
   # Установить зависимости
   npm install vue@2 jquery bootstrap webpack
   
   # Восстановить структуру
   mkdir -p src/components src/services
   ```

2. Создать `package.json`:
   ```json
   {
     "name": "smofast-extension",
     "version": "2.1.0",
     "scripts": {
       "dev": "webpack --mode development --watch",
       "build": "webpack --mode production",
       "lint": "eslint src/",
       "test": "jest"
     }
   }
   ```

3. Настроить Webpack:
   ```javascript
   // webpack.config.js
   module.exports = {
     entry: './src/popup.js',
     output: {
       path: path.resolve(__dirname, 'dist'),
       filename: 'popup.bundle.js'
     }
   }
   ```

### Структура проекта (рекомендуемая)

```
src/
├── components/
│   ├── App.vue
│   ├── TaskTable.vue
│   └── OrderTable.vue
├── services/
│   ├── api.js
│   └── auth.js
├── styles/
│   └── main.css
├── popup.js
└── background.js

dist/
├── popup.bundle.js
├── background.bundle.js
└── manifest.json

tests/
├── components/
└── services/

docs/
├── API.md
└── DEVELOPMENT.md
```

## 🔄 План миграции

### Фаза 1: Восстановление (1-2 недели)
- [ ] Восстановить исходный код из source maps
- [ ] Настроить среду разработки
- [ ] Добавить TypeScript
- [ ] Настроить ESLint/Prettier

### Фаза 2: Оптимизация (2-3 недели)  
- [ ] Уменьшить размер bundle
- [ ] Заменить jQuery на нативный JS
- [ ] Обновить Vue.js и Bootstrap
- [ ] Оптимизировать производительность

### Фаза 3: Безопасность (1 неделя)
- [ ] Добавить CSP
- [ ] Исправить XSS уязвимости
- [ ] Обновить разрешения
- [ ] Аудит зависимостей

### Фаза 4: Manifest v3 (1 неделя)
- [ ] Мигрировать на Manifest v3
- [ ] Обновить API calls
- [ ] Тестирование совместимости
- [ ] Финальное тестирование

## 📈 Метрики качества

| Параметр | Текущее | Цель | Статус |
|----------|---------|------|---------|
| Bundle size | ~800KB | ~250KB | ❌ |
| Load time | 300-500ms | 100-150ms | ❌ |
| Security score | Низкий | Высокий | ❌ |
| Lighthouse | 60-70 | 85-95 | ❌ |
| TypeScript | ❌ | ✅ | ❌ |
| Tests | ❌ | ✅ | ❌ |
| CSP | ❌ | ✅ | ❌ |
| Manifest v3 | ❌ | ✅ | ❌ |

## 🤝 Участие в разработке

Проект нуждается в активной разработке и улучшениях:

1. **Критические задачи:**
   - Миграция на Manifest v3
   - Исправления безопасности
   - Оптимизация производительности

2. **Желательные улучшения:**
   - Добавление тестов
   - Рефакторинг кода
   - Улучшение документации

### Как помочь

1. Fork репозиторий
2. Создайте feature branch
3. Внесите изменения
4. Добавьте тесты
5. Создайте Pull Request

## 📄 Лицензия

[MIT License](LICENSE) © 2023 SVIATOSLAV GUSEV

## 📞 Поддержка

- **Issues:** [GitHub Issues](https://github.com/govRosMedia/SMOFast-Job-and-order-management/issues)
- **Документация:** См. файлы `*_REPORT.md`
- **Контакты:** См. информацию в [LICENSE](LICENSE)

## 🏷️ Версии

- **v2.1** (текущая) - Стабильная версия с известными проблемами
- **v3.0** (планируется) - Manifest v3, TypeScript, оптимизации

---

**⚠️ Внимание:** Этот проект требует значительной модернизации для соответствия современным стандартам безопасности и производительности. См. детали в диагностических отчетах.