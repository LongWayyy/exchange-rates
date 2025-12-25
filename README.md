# Currency App - Тестовое задание

Веб-приложение для отображения курсов валют ЦБ РФ.

## Стек технологий
- Backend: Node.js, Express, MongoDB
- Frontend: Vue.js
- Дополнительно: Mongo Compose

## Установка и запуск


1. Запуск MongoDB локально
2. Настройка backend:
```bash
cd backend
npm install
cp .env.example .env
npm run dev

## пути
currency-app/
├── backend/
│   ├── src/
│   │   ├── controllers/          #  Обрабатывает логику приложения
│   │   │   └── currencyController.js
│   │   ├── routes/               #  Маршруты (роутинг) Связывает URL с контроллерами
│   │   │   └── currency.js       # Куда идти для получения истории и курсов
│   │   ├── services/             
│   │   │   └── cbrService.js    # Запрос API
│   │   ├── models/               
│   │   │   └── History.js       # Описание как хранить данные в БД
│   │   ├── config/               #  Конфигурация
│   │   │   └── database.js
│   │   └── app.js               #  Главный файл
│   ├── .env                     #  Настройки окружения
│   └── package.json             #  Зависимости
└── frontend/index.html          #  Весь фронтенд
## currencyController.js 
// Бизнес-логика:
async getCurrencyRates(req, res) {
  1. Получить данные из сервиса
  2. Сохранить в БД  
  3. Вернуть ответ
}
##cbrService.js
async getCurrentAndPreviousRates() {
  1. Запрос к API ЦБ
  2. XML → JSON
  3. Поиск рабочего дня
}

##app.js               
#  Главный файл с 3мя эндпоинтами, currency - курсы валют, history - история запросов, stats - статистика
Что делает:

Принимает запросы от фронтенда

Вызывает сервис ЦБ для получения курсов

Сохраняет данные в MongoDB

Возвращает JSON ответ

##frontend/index.html  
Основные функции:

fetchCurrencyRates() - запрос курсов

displayCurrencyRates() - карточки валют

getHistory() - история запросов 