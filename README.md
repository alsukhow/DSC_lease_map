# ISD — Leasing Map

Интерактивная карта аренды (React + Vite).

## Запуск локально

Нужен установленный Node.js (версия 18+). Проверить: `node -v`.
Если нет — поставить с https://nodejs.org (LTS).

```bash
npm install
npm run dev
```

Откроется на http://localhost:5173

## Где данные

Весь контент зон — в массиве `ZONES` вверху файла `src/App.jsx`.
Это точка свопа на Google Sheets / API в будущем.
Аренда/м² считается автоматически (rentYear / sqm) — руками не вводить.

Чтобы добавить зону — один объект в `ZONES`:

```js
{
  id: "Z3",
  name: "Название",
  sqm: 1000,
  rentYear: 200000,
  status: "available", // available | leased | pending
  points: [[x, y], [x, y], ...], // координаты 0–100 по обеим осям
}
```

## Сборка для деплоя (Vercel / статика)

```bash
npm run build
```

Готовые файлы появятся в папке `dist/`. Их можно залить на Vercel,
Netlify или GitHub Pages.

## Деплой на Vercel (ссылка для инвестора)

1. Запушить проект в репозиторий на GitHub.
2. На vercel.com → New Project → выбрать репозиторий.
3. Framework Preset определится как Vite автоматически. Deploy.
4. Получите публичный URL.
