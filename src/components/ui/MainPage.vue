<script setup>
import { ref } from "vue";

/*  dropdown  */
let isActive = ref(false);

function toggleIsActiveClass() {
  isActive.value = !isActive.value;
}
/*  modal  */
let isOpen = ref(false);

function toggleIsOpenClass() {
  isOpen.value = !isOpen.value;
}
</script>

<template>
  <main class="main">
    <section id="buttons" class="section">
      <h2 class="title">1. Кнопки</h2>
      <button class="btn">Кнопка</button>
      <button class="btn btn--rounded">Кнопка</button>
    </section>

    <section id="tooltips" class="section">
      <h2 class="title">2. Подсказки</h2>
      <span
        class="tooltip link"
        data-tooltip="Текст какой либо подсказки при наведении на текст"
        >Подсказка</span
      >
    </section>

    <section id="dropdown" class="section">
      <h2 class="title">3. Выпадающее меню</h2>
      <div class="dropdown">
        <a href="#" class="link" @click="toggleIsActiveClass"
          >Выпадающее меню</a
        >
        <div
          class="dropdown__drop"
          :class="{ 'dropdown__drop--active': isActive }"
        >
          <a href="#" class="dropdown__drop-item">Элемент 1</a>
          <a href="#" class="dropdown__drop-item">Элемент 2</a>
          <a href="#" class="dropdown__drop-item">Элемент 3</a>
        </div>
      </div>
    </section>

    <section id="checkbox" class="section">
      <h2 class="title">4. checkbox, switch</h2>
      <div>
        <div class="switch">
          <input type="checkbox" name="switch1" id="switch1" />
          <label for="switch1" class="switch__label"
            >Тексе какого то свича</label
          >
        </div>
      </div>

      <div>
        <div class="switch">
          <input type="checkbox" name="switch2" id="switch2" disabled />
          <label for="switch2" class="switch__label"
            >Тексе какого то свича</label
          >
        </div>
      </div>

      <div>
        <div class="checkbox">
          <input type="checkbox" name="check1" id="check1" />
          <label for="check1" class="checkbox__label"
            >Тексе какого то чекбокса</label
          >
        </div>
      </div>

      <div>
        <div class="checkbox">
          <input type="checkbox" name="check2" id="check2" disabled />
          <label for="check2" class="checkbox__label"
            >Тексе какого то чекбокса</label
          >
        </div>
      </div>
    </section>

    <section id="input" class="section">
      <h2 class="title">5. Поля ввода</h2>
      <div style="width: 440px">
        <div class="field">
          <input
            type="text"
            class="field__control"
            placeholder="Введите текст"
          />
        </div>

        <div class="field">
          <span class="field__icon"></span>
          <input type="text" class="field__control" placeholder="Поиск" />
        </div>
      </div>
    </section>

    <section id="menubar" class="section">
      <h2 class="title">6. Меню сайта</h2>
      <nav class="menubar">
        <a href="#" class="menubar__brand">Logo</a>
        <ul class="menubar__nav">
          <li><a href="#" class="menubar__nav-link">О компании</a></li>
          <li><a href="#" class="menubar__nav-link">Услуги</a></li>
          <li><a href="#" class="menubar__nav-link">Кейсы</a></li>
          <li><a href="#" class="menubar__nav-link">Отзывы</a></li>
          <li><a href="#" class="menubar__nav-link">Контакты</a></li>
        </ul>
      </nav>

      <nav class="menubar menubar--light">
        <a href="#" class="menubar__brand">Logo</a>
        <ul class="menubar__nav">
          <li><a href="#" class="menubar__nav-link">О компании</a></li>
          <li><a href="#" class="menubar__nav-link">Услуги</a></li>
          <li><a href="#" class="menubar__nav-link">Кейсы</a></li>
          <li><a href="#" class="menubar__nav-link">Отзывы</a></li>
          <li><a href="#" class="menubar__nav-link">Контакты</a></li>
        </ul>
      </nav>
    </section>

    <section id="modal" class="section">
      <h2 class="title">7. Модальные окна</h2>
      <button class="btn" @click="toggleIsOpenClass()">Показать модалку</button>
      <div class="modal" :class="{ 'modal--active': isOpen }">
        <div class="modal__window">
          <h2 class="modal__window-title">Заголовок окна</h2>
          <button class="modal__window-close" @click="toggleIsOpenClass">
            <span class="close__icon"></span>
          </button>
          <div class="modal__body">
            <span class="modal__body-label">Любой контент</span>
          </div>
        </div>
        <div class="modal__overlay"></div>
      </div>
    </section>

    <section id="cards" class="section">
      <h2 class="title">8. Карточки</h2>

      <article class="card">
        <img class="card__image" src="../../images/post.jpg" />
        <div class="card__body">
          <h3 class="card__title">Заголовок карточки</h3>
          <ul class="card__params">
            <li>
              <img
                class="card__params-icon"
                src="../../images/icons/visibel.svg"
              />3,4k
            </li>
            <li>
              <img
                class="card__params-icon"
                src="../../images/icons/message.svg"
              />152
            </li>
            <li>
              <time
                ><img
                  class="card__params-icon"
                  src="../../images/icons/calendar.svg"
                />11 февраля, 19:25</time
              >
            </li>
          </ul>
          <p class="card__text">
            Lorem ipsum dolor sit amet consectetur adipisicing elit. Doloribus
            excepturi dicta amet maxime blanditiis sunt quidem consequatur
            similique laboriosam, magnam mollitia pariatur corporis minima fuga
            voluptate unde, dolore consectetur iste!
          </p>
          <button class="btn">Читать</button>
        </div>
      </article>

      <br />
      <br />

      <article class="card-2">
        <div class="card-2__body">
          <h3 class="card-2__title">Заголовок карточки</h3>
          <ul class="card-2__params">
            <li>
              <img
                class="card__params-icon"
                src="../../images/icons/visibel.svg"
              />3,4k
            </li>
            <li>
              <img
                class="card__params-icon"
                src="../../images/icons/message.svg"
              />152
            </li>
            <li>
              <time
                ><img
                  class="card__params-icon"
                  src="../../images/icons/calendar.svg"
                />11 февраля, 19:25</time
              >
            </li>
          </ul>
        </div>
      </article>
    </section>
  </main>
</template>

<style scoped></style>
