# Тестовое задание для компании Matrix

Проект представляет собой веб-приложение для управления портфелем активов с обновлением данных в реальном времени. Приложение позволяет добавлять, удалять и отслеживать активы, такие как криптовалюты, с использованием WebSocket для получения актуальных цен. Реализовано с использованием React, TypeScript, Redux Toolkit и SCSS, с учетом производительности и доступности.

## Основные возможности

- Отображение списка активов с полями: название, количество, текущая цена, общая стоимость, изменение за 24 часа (в процентах), доля в портфеле.
- Добавление активов через форму с локальным сохранением данных.
- Удаление активов по клику на кнопку.
- Обновление цен в реальном времени через WebSocket (Binance API: `wss://stream.binance.com:9443/stream`).
- Виртуализация списка для поддержки более 100 активов.
- Адаптивный дизайн с анимациями и базовой поддержкой доступности (a11y).
- Аналитика портфеля (график распределения активов).

## Требования для запуска

- Node.js (версия 18 или выше)
- Yarn (рекомендуется, но можно использовать npm)

## Инструкции по запуску

1. **Склонируйте репозиторий:**
   ```bash
   git clone https://github.com/djoreh64/Matrix.git
   cd Matrix
   ```

2. **Установите зависимости:**
   ```bash
   yarn install
   ```

3. **Запустите проект в режиме разработки:**
   ```bash
   yarn dev
   ```
   Приложение будет доступно по адресу `http://localhost:3000`.

4. **Сборка для продакшена:**
   ```bash
   yarn build
   yarn start
   ```

## Использованные библиотеки

- **Next.js** — фреймворк для React с SSR и оптимизацией.
- **React** и **React DOM** — библиотека для построения интерфейса.
- **TypeScript** — типизация для надежности кода.
- **Redux Toolkit** и **React-Redux** — управление состоянием приложения.
- **Sass** — препроцессор для стилей.
- **UUID** — генерация уникальных идентификаторов для активов.
- **Recharts** — библиотека для построения графиков (аналитика портфеля).
- **Framer Motion** — анимации интерфейса.
- **Lucide React** — иконки для UI.
- **React Focus Lock** — улучшение доступности для модальных окон.

## Архитектура проекта

```
src/
├── app/               # Корневой каталог Next.js App Router
│   ├── globals.css    # Глобальные стили
│   ├── layout.tsx     # Главный layout приложения
│   ├── page.tsx       # Главная страница
│   ├── providers.tsx  # Провайдеры состояния и контекста
├── components/        # UI-компоненты
│   ├── AssetForm/     # Форма добавления активов
│   ├── AssetTable/    # Таблица с активами
│   ├── PieChartComponent/ # График портфеля
│   └── PortfolioOverview/ # Обзор портфеля
├── store/             # Управление состоянием (Redux Toolkit)
│   ├── store.ts       # Конфигурация Redux Store
│   └── slices/        # Слайсы состояния
│       └── portfolioSlice.ts
├── hooks/             # Кастомные React-хуки
│   └── useMobile.ts   # Определение мобильного устройства
├── utils/             # Вспомогательные функции
│   └── parseCosts.ts  # Форматирование стоимости
├── types/             # Глобальные типы TypeScript
│   └── index.ts
├── consts/            # Константы
│   └── index.ts

```