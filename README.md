# Currency App - Тестовое задание

Веб-приложение для отображения курсов валют ЦБ РФ.

## Стек технологий
- Backend: Node.js, Express, MongoDB
- Frontend: Vue.js
- Дополнительно: MongoDB Compose

## Запуск

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
│   │   ├── routes/               #  Маршруты  
│   │   │   └── currency.js       # Куда идти для получения истории и курсов, связывает URL с контроллерами
│   │   ├── services/             
│   │   │   └── cbrService.js    # Запрос API
│   │   ├── models/               
│   │   │   └── History.js       # Описание как хранить данные в БД
│   │   ├── config/               
│   │   │   └── database.js      #Работа с базой данных
│   │   └── app.js               #  Главный файл 
│   ├── .env                     #  Настройки окружения
│   └── package.json            
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

1.Принимает запросы от фронтенда
2.Вызывает сервис ЦБ для получения курсов
3.Сохраняет данные в MongoDB
4.Возвращает JSON ответ



##frontend/index.html  
Основные функции:

1.fetchCurrencyRates() - запрос курсов
2.displayCurrencyRates() - карточки валют
3.getHistory() - история запросов 



