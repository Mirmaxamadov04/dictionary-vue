<template>
  <header class="header">
    <div class="container">
      <img src="@/images/book.svg" alt="" class="header__logo" />

      <nav class="nav">
        <select class="nav__select">
          <option class="nav__option" value="Sans Serif">Sans Serif</option>
          <option class="nav__option" value="Serif">Serif</option>
          <option class="nav__option" value="Mono">Mono</option>
          <img src="@/images/font-change.svg" alt="" />
        </select>

        <button class="on-off">
          <img src="@/images/off.svg" alt="" class="on-off__image" />
        </button>

        <button class="moon">
          <svg
            width="22"
            height="22"
            viewBox="0 0 22 22"
            fill="none"
            xmlns="http://www.w3.org/2000/svg"
            class="moon__image"
          >
            <path
              fill-rule="evenodd"
              clip-rule="evenodd"
              d="M1 10.449C0.998458 12.8283 1.80169 15.1383 3.27914 17.0033C4.75659 18.8683 6.82139 20.1788 9.13799 20.7218C11.4545 21.2647 13.8866 21.0082 16.039 19.994C18.1912 18.9797 19.9373 17.2673 20.9931 15.1352C11.5442 15.1352 6.85799 10.4479 6.85799 1C5.09842 1.87311 3.61767 3.22033 2.58266 4.88981C1.54765 6.5593 0.999502 8.48469 1 10.449Z"
              stroke="#757575"
              stroke-width="1.5"
              stroke-linecap="round"
              stroke-linejoin="round"
            />
          </svg>
        </button>
      </nav>
    </div>
  </header>
</template>

<style>
.header .container {
  display: flex;
  justify-content: space-between;
  padding-top: 20px;
}

.header__logo {
  cursor: pointer;
}

.nav__button {
  font-weight: 700;
  font-size: 18px;
  line-height: 24px;
  text-align: right;
  color: #2d2d2d;
  background: transparent;
  border: none;
  transition: 0.3s all ease;
  cursor: pointer;
}
.nav {
  margin-top: -10px;
  display: flex;
}
.on-off {
  background: transparent;
  border: none;
  margin-left: 20px;
  margin-top: 15px;
  cursor: pointer;
  transition: 0.3s all ease;
}

.nav__select {
  margin-top: 15px;
  margin-left: -30px;
  background: transparent;
  border: none;
  outline: none;
}

.nav__select::after {
  display: block;
  content: "";
  height: 32px;
  width: 1px;
  background: #e9e9e9;
  border: 1px solid;
}

.moon {
  background: transparent;
  border: none;
  margin-left: 20px;
}

.moon__image {
  margin-top: 15px;
}

.moon-clicked .moon__image path {
  stroke: #a445ed;
}
</style>
