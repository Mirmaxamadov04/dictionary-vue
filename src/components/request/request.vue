<template>
  <section class="request">
    <div class="container">
      <form action="" class="form" @submit.prevent="$emit('woord', word)">
        <input
          type="text"
          class="form__input"
          placeholder="Search for any key word"
          v-model="word"
        />
        <span class="form__validation"></span>
        <button class="form__button">
          <img src="@/images/search.svg" alt="" class="form__button-img" />
        </button>
      </form>
    </div>
  </section>
</template>

<script setup>
import { ref } from "vue";
const word = ref("");
</script>

<style>
.request {
  margin-top: 50px;
}

.form {
  position: relative;
  text-align: center;
  width: 100%;
  margin: 0 auto;
}

.form__button {
  position: absolute;
  border: none;
  background: transparent;
  top: 20px;
  right: 25px;
}

.form__input:focus {
  border: 1px solid #a445ed;
}

.form__input {
  position: relative;
  margin: 0 auto;
  width: 100%;
  font-weight: 700;
  font-size: 20px;
  line-height: 24px;
  color: #2d2d2d;
  position: relative;
  padding: 20px 24px;
  background: #f4f4f4;
  border-radius: 16px;
  border: none;
  outline: none;
}

.form__input::placeholder {
  font-weight: 700;
  font-size: 20px;
  line-height: 24px;
  color: #2d2d2d;
  mix-blend-mode: normal;
  opacity: 0.25;
}

.form__button-img {
  position: relative;
  top: 2px;
  right: 8px;
  cursor: pointer;
}

.border {
  border: 1px solid #921e4e;
}
</style>
