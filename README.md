# Restaurant Management System - AI-Powered Platform

Полноценная интеллектуальная система управления рестораном с интеграцией искусственного интеллекта. Система включает три зоны: публичная часть (Client), официанты (Staff) и администрирование с AI-аналитикой (Admin).

## 🚀 Ключевые возможности

### 🤖 AI-возможности
- **Автоматические дайджесты** - ежедневные AI-отчёты о работе ресторана
- **Прогнозирование спроса** - предсказание популярности блюд
- **Интеллектуальные рекомендации** - советы по оптимизации меню, персонала, ценообразованию
- **AI-чат ассистент** - интерактивный помощник для менеджеров
- **Анализ трендов** - выявление паттернов в поведении клиентов

### 📊 Аналитика
- Полная панель бизнес-метрик в реальном времени
- Производительность меню и категорий
- Метрики эффективности персонала
- Экспорт данных (CSV, Excel, PDF)
- Системный мониторинг и health checks

### 🔔 Уведомления
- Real-time уведомления о важных событиях
- Интеграция с AI-инсайтами
- Приоритезация по важности
- История всех уведомлений

## Технологии

### Frontend
- **Next.js 14** (App Router)
- **React 18** с TypeScript
- **TailwindCSS** для стилизации
- **TanStack Query v5** для управления данными
- **Framer Motion** для анимаций
- **Recharts** для графиков и аналитики
- **Zod** для валидации

### Backend (требуется реализация)
- **.NET 8 Web API**
- **PostgreSQL 15+** с расширениями для AI
- **OpenAI API** (GPT-4 Turbo)
- **Redis** для кэширования
- **Hangfire** для фоновых задач

## Структура проекта

```
├── app/                    # Next.js App Router страницы
│   ├── (public)/          # Публичные маршруты (/, /menu, /booking)
│   ├── staff/             # Маршруты для официантов
│   ├── admin/             # Маршруты для администраторов
│   └── api/               # API роуты (если нужны)
├── components/            # React компоненты
│   ├── ui/               # Базовые UI компоненты
│   └── features/         # Бизнес-компоненты
├── lib/                   # Утилиты и хелперы
│   ├── api/              # API клиент
│   ├── hooks/            # Кастомные React хуки
│   └── utils/            # Вспомогательные функции
├── types/                 # TypeScript типы
├── constants/             # Константы приложения
└── public/               # Статические файлы

```

## Функциональность

### 🌐 Client (Публичная часть)
- Просмотр меню по категориям с фильтрацией
- Онлайн-бронирование столов
- Поиск брони по имени + 4 цифрам телефона
- Опциональный предзаказ блюд

### 👔 Staff (Официанты)
- Открытие и ведение заказов
- Добавление позиций в заказ
- Закрытие заказов
- Печать чеков в формате методички
- Доступ к AI-рекомендациям по блюдам

### 🎯 Admin (Администраторы)

#### Базовые функции
- CRUD операции с меню и столами
- Управление бронированиями
- Управление официантами
- Детальные отчёты по всем метрикам

#### AI-панель управления
- **Дневные дайджесты** - автоматический анализ работы
- **Прогнозы спроса** - планирование закупок и персонала
- **Рекомендации** - действенные советы по улучшению:
  - Оптимизация меню
  - Управление персоналом
  - Стратегии ценообразования
  - Маркетинговые инсайты
- **AI-чат** - интерактивные вопросы и ответы
- **История AI-запросов** - аудит и анализ

#### Аналитика
- **Dashboard** - общая картина бизнеса
- **Выручка** - детализация по периодам, категориям
- **Меню** - производительность блюд и категорий
- **Персонал** - эффективность официантов
- **Клиенты** - анализ поведения и лояльности
- **Экспорты** - данные в CSV, Excel, PDF

## Установка и запуск

```bash
# Установка зависимостей
npm install

# Копирование переменных окружения
cp .env.example .env

# Запуск в режиме разработки
npm run dev

# Сборка для продакшена
npm run build

# Запуск продакшен-сборки
npm start
```

## Скрипты

- `npm run dev` - запуск в режиме разработки
- `npm run build` - сборка проекта
- `npm run start` - запуск собранного проекта
- `npm run lint` - проверка кода линтером
- `npm run type-check` - проверка типов TypeScript

## 🔐 Роли и доступ

- **client** - публичный доступ (/, /menu, /booking)
- **waiter** - доступ к /staff/**, AI-рекомендации по блюдам
- **manager** - доступ к /admin/**, аналитика, AI-инсайты
- **admin** - полный доступ ко всем функциям

## 📚 Документация

- [AI API Reference](./docs/AI_API.md) - полная документация REST API
- [Backend Implementation Guide](./docs/BACKEND_IMPLEMENTATION.md) - руководство по реализации backend
- [Technical Specification](./docs/AI_FEATURES.md) - техническая спецификация AI-функций
- [Project Summary](./PROJECT_SUMMARY.md) - обзор проекта
- [Quick Start](./QUICKSTART.md) - быстрый старт
- [Roadmap](./ROADMAP.md) - план развития

## 🗄️ База данных

Проект включает SQL миграции для PostgreSQL:
- `backend/migrations/002_ai_analytics.sql` - схема для AI и аналитики (8+ новых таблиц)

Ключевые таблицы:
- `AiRequests` - история AI-запросов для аудита
- `DailyDigests` - сохранённые дайджесты
- `DishForecasts` - прогнозы спроса на блюда
- `AiRecommendations` - AI-рекомендации
- `Notifications` - система уведомлений
- `UserSessions` - трекинг активности
- `OrderAnalytics`, `MenuAnalytics`, `ClientPreferences` - детальная аналитика

## 🚀 Быстрый старт

### Frontend
```bash
# Установка зависимостей
npm install

# Настройка переменных окружения
cp .env.example .env

# Запуск в режиме разработки
npm run dev
```

### Backend
```bash
# Применить миграции
psql -U postgres -d restaurant_db -f backend/migrations/002_ai_analytics.sql

# Настроить OpenAI API ключ в appsettings.json
# Запустить .NET проект
cd backend/Restaurant.Api
dotnet run
```

## 🧪 Тестирование

```bash
# Frontend
npm run test
npm run test:watch

# Backend
cd backend
dotnet test
```

## 📦 Deployment

### Production Build
```bash
# Frontend
npm run build
npm start

# Backend
cd backend/Restaurant.Api
dotnet publish -c Release -o ./publish
```

### Docker (опционально)
```bash
docker-compose up -d
```

## 🔧 Требования

### Frontend
- Node.js 18+
- npm или yarn

### Backend
- .NET 8 SDK
- PostgreSQL 15+
- Redis (для кэширования)
- OpenAI API ключ

## 🌟 Основные компоненты

### Frontend
- `components/features/ai/AiChatWidget.tsx` - AI чат-виджет
- `components/features/notifications/NotificationBell.tsx` - система уведомлений
- `components/features/metrics/MetricCards.tsx` - переиспользуемые карточки метрик
- `app/admin/ai-insights/page.tsx` - AI-панель управления
- `lib/hooks/useAi.ts` - React hooks для AI
- `lib/hooks/useAnalytics.ts` - React hooks для аналитики

### Backend (требуется реализация)
- `AiService.cs` - основной сервис AI
- `OpenAiService.cs` - интеграция с OpenAI
- `AnalyticsService.cs` - сервис аналитики
- `NotificationService.cs` - система уведомлений

## 🤝 Вклад в проект

Проект открыт для улучшений и расширений. См. [ROADMAP.md](./ROADMAP.md) для планируемых функций.

## 📄 Лицензия

Проект разработан для учебных и коммерческих целей.
