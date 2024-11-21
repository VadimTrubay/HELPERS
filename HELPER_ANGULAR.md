1. npm install -g @angular/cli

2. ng version

3. При работе на Windows и выполнении команд в PowerShell вместо командной строки стоит учитывать, что по умолчанию
   выполнение скриптов в PowerShell отключено. Чтобы разрешить выполнение скриптов PowerShell (что требуется для npm),
   необходимо выполнить следующую команду:

4. Set-ExecutionPolicy -Scope CurrentUser -ExecutionPolicy RemoteSigned

5. ng update

6. ng new <project-name>

7. cd <project-name>

8. ng serve or npm start

# Tailwind

npm install -D tailwindcss postcss autoprefixer
npx tailwindcss init -p

#tailwind.config.js

/** @type {import('tailwindcss').Config} */
module.exports = {
content: [
"./src/**/*.{html,ts}",
],
theme: {
extend: {},
},
plugins: [],
}

#src/styles.css
@tailwind base;
@tailwind components;
@tailwind utilities;

ng g s services/error --skip-tests

ng g c components/global-error --skip-tests

ng g pipe pipes/filter-products --skip-tests

Вот список некоторых популярных украинских библиотек и решений для Angular, которые могут помочь вам расширить
функциональность вашего приложения:

1. ngx-bootstrap
   Описание: Библиотека компонентов Bootstrap для Angular с поддержкой темизации и адаптивной вёрстки. Поддерживает
   модальные окна, карусели, уведомления и многое другое.
   Сайт: ngx-bootstrap
2. NG-ZORRO
   Описание: Компоненты Angular в стиле Ant Design. Подходит для создания корпоративных интерфейсов с поддержкой
   множества UI-элементов.
   Сайт: NG-ZORRO
3. Nebular
   Описание: Набор UI-компонентов для Angular, созданный Akveo. Подходит для создания современных веб-приложений с
   темизацией и поддержкой адаптивности.
   Сайт: Nebular
4. PrimeNG
   Описание: Мощный набор UI-компонентов с поддержкой множества тем и адаптивного дизайна. Включает таблицы, графики,
   формы и многое другое.
   Сайт: PrimeNG
5. Angular Material
   Описание: Официальная библиотека Material Design для Angular с поддержкой компонентов, таких как кнопки, карточки,
   модальные окна и таблицы.
   Сайт: Angular Material
6. ngx-translate
   Описание: Библиотека для интернационализации Angular-приложений. Позволяет легко добавлять поддержку перевода для
   динамического текста.
   Сайт: ngx-translate
7. NgRx
   Описание: Библиотека для управления состоянием в Angular-приложениях, основанная на архитектуре Redux. Поддерживает
   эффекты для работы с асинхронными данными.
   Сайт: NgRx
8. Swimlane ngx-charts
   Описание: Библиотека для создания интерактивных и адаптивных графиков и диаграмм в Angular.
   Сайт: ngx-charts
9. Angular Flex-Layout
   Описание: Библиотека для создания адаптивной и гибкой вёрстки с использованием CSS Flexbox API.
   Сайт: Angular Flex-Layout
10. ngx-permissions
    Описание: Библиотека для управления ролями и правами доступа в Angular-приложениях.
    Сайт: ngx-permissions
    Эти библиотеки помогут вам легко расширить функциональность вашего приложения и создать адаптивные, красивые и
    производительные интерфейсы.

Вот список популярных библиотек компонентов для Angular, которые помогут упростить создание пользовательского интерфейса
и добавить в приложение различные функции:

1. Angular Material
   Описание: Официальная библиотека Material Design для Angular. Включает готовые компоненты, такие как кнопки,
   карточки, таблицы, и многое другое.
   Сайт: Angular Material
2. PrimeNG
   Описание: Многофункциональная библиотека с множеством UI-компонентов, таких как календарь, графики, таблицы и
   карусели. Поддерживает адаптивный дизайн и темы.
   Сайт: PrimeNG
3. NG-ZORRO
   Описание: Компоненты, основанные на Ant Design. Идеально подходят для создания корпоративных и административных
   интерфейсов.
   Сайт: NG-ZORRO
4. Nebular
   Описание: Современные UI-компоненты от Akveo с поддержкой темизаций и адаптивности. Подходит для создания
   корпоративных приложений.
   Сайт: Nebular
5. ng-bootstrap
   Описание: Angular-совместимые компоненты Bootstrap. Легко интегрируются в приложение и поддерживают адаптивную
   верстку.
   Сайт: ng-bootstrap
6. ngx-bootstrap
   Описание: Еще одна библиотека компонентов Bootstrap для Angular. Обеспечивает модальные окна, выпадающие списки и
   другие элементы.
   Сайт: ngx-bootstrap
7. DevExtreme Angular UI Components
   Описание: Набор мощных компонентов для работы с данными, включая таблицы, графики, формы и редакторы.
   Сайт: DevExtreme Angular
8. Kendo UI for Angular
   Описание: Коммерческая библиотека с компонентами премиум-класса для корпоративных приложений. Включает таблицы,
   диаграммы, графики и многое другое.
   Сайт: Kendo UI for Angular
9. Clarity
   Описание: Библиотека компонентов от VMware, специально разработанная для создания административных панелей с упором
   на простоту и производительность.
   Сайт: Clarity
10. Swimlane ngx-datatable
    Описание: Высокопроизводительная таблица данных для Angular с поддержкой больших наборов данных, адаптивности и
    темизаций.
    Сайт: ngx-datatable
    Эти библиотеки позволят вам создать мощные и современные интерфейсы с минимальными усилиями.


Команда ng generate (ng g) в Angular CLI позволяет генерировать различные сущности проекта. Вот что можно сгенерировать:

1. Компоненты
   bash
   Copy code
   ng g c component-name
   Создает компонент, включая:

HTML-шаблон
CSS (или другой стиль, например SCSS, в зависимости от конфигурации проекта)
Файл TypeScript с логикой компонента
Тестовый файл (.spec.ts, если включены тесты)
2. Модули
   bash
   Copy code
   ng g m module-name
   Создает Angular модуль:

С .module.ts файлом
(Опционально) добавляет в корневой модуль, если указать флаг --module:
bash
Copy code
ng g m module-name --module app
3. Директивы
   bash
   Copy code
   ng g d directive-name
   Создает директиву с соответствующими файлами.

4. Сервисы
   bash
   Copy code
   ng g s service-name
   Создает сервис, добавляет его в providers (если настроено).

5. Каналы (Pipes)
   bash
   Copy code
   ng g p pipe-name
   Создает пользовательский pipe.

6. Гварды (Guards)
   bash
   Copy code
   ng g g guard-name
   Создает guard с возможностью выбора типа: CanActivate, CanActivateChild, CanLoad, и др.

7. Интерфейсы
   bash
   Copy code
   ng g i interface-name
   Создает интерфейс TypeScript.

8. Классы
   bash
   Copy code
   ng g cl class-name
   Создает класс TypeScript.

9. Перечисления (Enums)
   bash
   Copy code
   ng g e enum-name
   Создает перечисление TypeScript.

10. Шаблоны (Schematics)
    С помощью Angular Schematics можно генерировать кастомные сущности.

Если хотите настроить параметры, например, указать inline-template или пропустить тесты:

bash
Copy code
ng g c component-name --inline-template --skip-tests