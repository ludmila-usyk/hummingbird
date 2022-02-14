# Parcel boilerplate

## Скрытые файлы

Включите отображение скрытых файлов и папок в проводнике своей операционной системы, иначе вы не
сможете выбрать и скопировать себе файлы настроек проекта, имена которых начинаются с точки.

## Зависимости

На компьютере должена быть установлена LTS-версия [Node.js](https://nodejs.org/en/) со всеми
дополнительными инструментами кроме **Chocolatey** - его ставить не нужно.

## Перед началом работы

Один раз на проект установить все зависимости.

```shell
npm ci
```

### Разработка

Запустить режим разработки.

```shell
npm run dev
```

Во вкладке браузера перейти по адресу [http://localhost:1234](http://localhost:1234).

### Деплой

Сборка будет автоматически собирать и деплоить продакшен версию проекта на GitHub Pages, в ветку
`gh-pages`, каждый раз когда обновляется ветка `main`. Например, после прямого пуша или принятого
пул-реквеста. Для этого необходимо в файле `package.json` отредактировать поле `homepage` и скрипт
`build`, заменив `имя_пользователя` и `имя_репозитория` на свои.

```json
"homepage": "https://имя_пользователя.github.io/имя_репозитория",
"scripts": {
  "build": "parcel build src/*.html --public-url /имя_репозитория/"
},
```

На всякий случай стоит зайти в настройки репозитория `Settings` > `Pages` и убедиться что продакшен
версии файлов раздаются из папки `/root` ветки `gh-pages`.

Через какое-то время живую страницу можно будет посмотреть по адресу указанному в отредактированном
свойстве `homepage`, например
[https://goitacademy.github.io/parcel-project-template](https://goitacademy.github.io/parcel-project-template).

## Файлы и папки

- Все паршалы файлов стилей должны лежать в папке `src/sass` и импортироваться в
  `src/sass/main.scss`
- Изображения добавляйте в папку `src/images`, заранее оптимизировав их. Сборщик просто копирует
  используемые изображения чтобы не нагружать систему оптимизацией картинок, так как на слабых
  компьютерах это может занять много времени.

  

  <ul class="portfolio-list">
<li class="item">
    <div class="front">
        <img src="" alt="" />
    </div>
    <div class="back">
        <span class="more-info">Lorem ipsum</span>
        <img src="" alt="" />
    </div>
    <h3 class="portfolio-title">work 1</h3>
    <p class="portfolio-description">
        Lorem ipsum
    </p>
</li>
/* portfolio section */
.portfolio-list {
  display: flex;
  flex-wrap: wrap;
  margin: -15px;
  justify-content: center;
}
.portfolio .container .description {
  margin-bottom: 30px;
}
.portfolio-list .item {
  position: relative;
  width: 320px;
  margin: 15px;
}
.front,
.back {
  transition: 1s;
  display: flex;
  justify-content: center;
  align-items: center;
  backface-visibility: hidden;
}
.back {
  transform: rotateY(180deg);
  position: absolute;
  top: 0;
  left: 0;
}
.portfolio-list .item:hover .front {
  transform: rotateY(180deg);
}
.portfolio-list .item:hover .back {
  transform: rotateY(360deg);
}
.more-info {
  position: absolute;
  top: 0;
  left: 0;
  top: 50%;
  left: 50%;
  transform: translate(-50%, -50%);
  width: 270px;
  height: 270px;
  padding-top: 23px;
  padding-bottom: 24px;
  padding-left: 30px;
  padding-right: 30px;
  font-weight: 500;
  font-size: 18px;
  line-height: 22px;
  text-align: center;
  background: rgba(255, 255, 255, 0.7);
}
.portfolio-title {
  font-weight: 600;
  font-size: 24px;
  line-height: 29px;
  text-transform: uppercase;
  color: red;
  margin: 0;
  margin-top: 15px;
}
.portfolio-description {
  margin: 0;
  font-weight: 500;
  font-size: 18px;
  line-height: 22px;
}