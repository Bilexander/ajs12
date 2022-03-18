### Описание

Ваша задача подключить Babel к проекту и настроить сборку с его использованием.

1. Установите Babel (`npm install --save-dev @babel/core @babel/cli @babel/preset-env`).
2. Установите CoreJS (`npm install core-js@3`).

2. Настройте скрипт запуска `build` для сборки с помощью `npm`. Для этого в секции `scripts` файла `package.json` пропишите:
```json
{
    ...
    "scripts": {
        ...
        "build": "babel src -d dist"
        ...
    }
}
```

3. Создайте конфиг `.babelrc` и пропишите `@babel/preset-env`:
```javascript
{
  "presets": [
    [
      "@babel/preset-env",
      {
        "useBuiltIns": "usage",
        "corejs": 3
      }
    ]
  ]
}
```

4. Создайте файл `src/app.js` со следующим содержимым:
```javascript
const characters = [
  {name: 'мечник', health: 10},
  {name: 'маг', health: 100},
  {name: 'маг', health: 0},
  {name: 'лучник', health: 0},
];

const alive = characters.filter(item => item.health > 0);
```

5. Удостоверьтесь, что проект собирается, если в консоли запустить команду `npm run build`, и в каталоге `dist` формируется преобразованный Babel код.

6. Добавьте каталог `dist` в `.gitignore`.

---
