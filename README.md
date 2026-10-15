# Атлас — Earth Explorer

Интерактивный 3D-глобус: вращение, масштабирование, выбор стран и территорий, поиск и перелёт к 30 городам.

## Локальный запуск

```sh
python3 -m http.server 8000 --directory dist
```

Откройте http://localhost:8000. Нужен современный браузер с WebGL. Сборка и установка зависимостей не нужны: Three.js и данные включены в репозиторий.

## Структура

- `dist/index.html` — интерфейс и import map.
- `dist/style.css` — адаптивные стили.
- `dist/app.js` — сцена Three.js, управление, география и поиск.
- `dist/vendor/` — Three.js 0.180.0 и OrbitControls.
- `dist/assets/earth.jpg` — текстура Земли.
- `dist/assets/countries.json` — упрощённые географические границы.
- `index.html` — входная страница GitHub Pages; использует ресурсы из `dist/`.
- `.nojekyll` — публикация статических файлов без обработки Jekyll.
- `.github/workflows/pages.yml` — проверка JavaScript и геоданных.

## GitHub Pages

Сайт: https://ytvee.github.io/earth/

Pages публикует ветку `main`, папку `/ (root)` (Deploy from a branch). В корне находится входная страница глобуса, ресурсы загружаются из `dist/`. Публикация запускается автоматически после push в main.

## Источники и ограничения

Three.js 0.180.0: https://github.com/mrdoob/three.js (MIT).
Текстура: https://threejs.org/examples/textures/planets/earth_atmos_2048.jpg.
Границы: https://github.com/datasets/geo-countries, Natural Earth (public domain), упрощены для браузера.

Границы схематичны и включают территории; их отображение не является заявлением о политическом статусе. Масштабирование приближает поверхность сферы, но не загружает улицы и здания. Города — ограниченная подборка, а не полный справочник.

Проверены синтаксис JS и наличие локальных ресурсов. Проверка взаимодействий в браузере ещё не выполнена.
