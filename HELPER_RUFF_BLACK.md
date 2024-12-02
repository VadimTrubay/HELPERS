Для Angular и TypeScript линтером, аналогичным Black для Python, является ESLint. Это мощный инструмент для статического
анализа кода, который помогает поддерживать единый стиль кодирования и выявлять потенциальные ошибки.

Почему ESLint?
Расширяемость: Вы можете использовать плагины и конфигурации, специально разработанные для Angular (например,
@angular-eslint).
Настраиваемость: Легко адаптируется под ваш стиль кодирования с помощью правил, которые можно включать или исключать.
Автоматическое исправление: Поддерживает автоматическую правку ряда ошибок и форматирования кода.
Установка ESLint для Angular
Установите зависимости:

bash
Copy code
ng add @angular-eslint/schematics
Сконвертируйте tslint.json (если мигрируете с TSLint):

bash
Copy code
ng g @angular-eslint/schematics:convert-tslint-to-eslint
Настройка конфигурации: angular.json будет автоматически обновлен для использования ESLint, и будет добавлен файл
.eslintrc.json.

Пример конфигурации .eslintrc.json для Angular
json
Copy code
{
"root": true,
"overrides": [
{
"files": ["*.ts"],
"extends": [
"eslint:recommended",
"plugin:@typescript-eslint/recommended",
"plugin:@angular-eslint/recommended"
],
"parserOptions": {
"project": "tsconfig.json",
"createDefaultProgram": true
}
},
{
"files": ["*.html"],
"extends": ["plugin:@angular-eslint/template/recommended"],
"parser": "@angular-eslint/template-parser"
}
]
}
Интеграция с редактором кода
Для лучшей интеграции:

VS Code: Установите расширение ESLint для подсветки ошибок и предупреждений.
WebStorm/IntelliJ: Настройте ESLint через Preferences/Settings > Languages & Frameworks > JavaScript > Code Quality
Tools > ESLint.
Форматирование кода
Если вы хотите автоматического форматирования кода, похожего на работу Black, то можно использовать Prettier:

Установите Prettier:

bash
Copy code
npm install --save-dev prettier
Интеграция с ESLint: Добавьте eslint-config-prettier для отключения правил ESLint, которые конфликтуют с Prettier.

bash
Copy code
npm install --save-dev eslint-config-prettier
Настройте конфигурацию: Добавьте "prettier" в extends вашего .eslintrc.json.

С таким набором инструментов ваш Angular проект будет поддерживать чистый, форматированный и легко читаемый код.

Чтобы запустить Prettier для всего проекта и привести весь код в соответствие с его правилами, выполните следующие шаги:

1. Убедитесь, что Prettier установлен:
   Если вы еще не установили Prettier в проекте, сделайте это с помощью следующей команды:

bash
Copy code
npm install --save-dev prettier

2. Создайте или настройте конфигурационный файл Prettier:
   Создайте файл .prettierrc или .prettierrc.json в корне вашего проекта, чтобы настроить параметры форматирования.
   Пример:

json
Copy code
{
"semi": true,
"singleQuote": true,
"printWidth": 80,
"tabWidth": 2,
"trailingComma": "es5"
}

3. Запуск Prettier для всего проекта:
   Вы можете использовать команду prettier для форматирования всех файлов в проекте.

Скрипт для форматирования всех файлов: Добавьте скрипт в package.json:

json
Copy code
"scripts": {
"format": "prettier --write \"src/**/*.{ts,js,json,css,scss,html}\""
}
Запуск скрипта:

bash
Copy code
npm run format

4. Альтернативный способ (однократный запуск):
   Вы также можете выполнить Prettier напрямую из командной строки:

bash
Copy code
npx prettier --write "src/**/*.{ts,js,json,css,scss,html}"

5. Интеграция с Git (Опционально):
   Если вы хотите автоматически запускать Prettier при коммите, можно использовать Husky и lint-staged:

Установите Husky и lint-staged:

bash
Copy code
npx husky-init && npm install
npm install --save-dev lint-staged
Настройте lint-staged в package.json:

json
Copy code
"lint-staged": {
"src/**/*.{ts,js,json,css,scss,html}": "prettier --write"
}
Настройте husky для использования lint-staged: В файле .husky/pre-commit добавьте строку:

bash
Copy code
npx lint-staged
Теперь Prettier будет запускаться при каждом коммите, чтобы форматировать измененные файлы.

# REACT
Для проекта на React настройка ESLint и Prettier будет немного отличаться, но общая структура процесса остается схожей. Вот как можно настроить ESLint и Prettier для React:

1. Установка зависимостей
   Установите ESLint и необходимые плагины для React:

bash
Copy code
npx eslint --init
Выберите следующие опции:

Тип файла: JavaScript или TypeScript, в зависимости от вашего проекта.
Framework: React.
Используемые стили: "Use a popular style guide" или "Answer questions about your style".
Установка зависимостей: Автоматически установите пакеты.
Если у вас TypeScript, дополнительно установите:

bash
Copy code
npm install --save-dev @typescript-eslint/parser @typescript-eslint/eslint-plugin
2. Установка Prettier и его интеграция
   Установите Prettier и необходимые пакеты:

bash
Copy code
npm install --save-dev prettier eslint-config-prettier eslint-plugin-prettier
3. Настройка конфигурации ESLint
   Настройте .eslintrc.json для интеграции с Prettier:

json
Copy code
{
"extends": [
"eslint:recommended",
"plugin:react/recommended",
"plugin:@typescript-eslint/recommended",
"plugin:prettier/recommended"
],
"plugins": ["react", "@typescript-eslint"],
"parser": "@typescript-eslint/parser",
"settings": {
"react": {
"version": "detect"
}
},
"rules": {
"prettier/prettier": "error"
}
}
4. Настройка конфигурации Prettier
   Создайте файл .prettierrc.json:

json
Copy code
{
"semi": true,
"singleQuote": true,
"printWidth": 80,
"tabWidth": 2,
"trailingComma": "es5"
}
5. Скрипт для форматирования всего проекта
   Добавьте скрипт для запуска Prettier в package.json:

json
Copy code
"scripts": {
"format": "prettier --write \"src/**/*.{js,jsx,ts,tsx,json,css,scss,html}\""
}
Запуск скрипта:

bash
Copy code
npm run format
6. Интеграция с Git (Опционально)
   Для автоматического форматирования при коммитах используйте Husky и lint-staged:

bash
Copy code
npx husky-init && npm install
npm install --save-dev lint-staged
Настройте lint-staged в package.json:

json
Copy code
"lint-staged": {
"*.{js,jsx,ts,tsx,json,css,scss,html}": "prettier --write"
}
7. Настройка Husky для Git-хуков
   Добавьте скрипт Husky:

bash
Copy code
npx husky add .husky/pre-commit "npx lint-staged"
Теперь при каждом коммите будет автоматически запускаться форматирование файлов с помощью Prettier.

С этими настройками ваш проект React будет использовать ESLint для проверки 
качества кода и Prettier для автоматического форматирования, что делает код более читаемым и стандартизированным.











