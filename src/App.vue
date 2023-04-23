<template>
  <div>
    <div1 />
    <request v-model="word" @woord="getDefinition" />
    <content :word="definition" />
    <contentmain
      v-for="(meaning, index) in definition.meanings"
      :key="index"
      :meanings="meaning"
    />
  </div>
</template>

<script setup>
import div1 from "./components/header/header.vue";
import request from "./components/request/request.vue";
import content from "./components/content/content.vue";
import contentmain from "./components/content__main/content-main.vue";
import { ref, shallowRef } from "vue";
const word = ref("");

const definition = shallowRef([]);

async function getDefinition(word) {
  const url = `https://api.dictionaryapi.dev/api/v2/entries/en`;
  const req = await fetch(`${url}/${word}`);
  const data = await req.json();
  definition.value = data[0];
  console.log(data);
  console.log(definition.value);
}
</script>

<style>
* {
  box-sizing: border-box;
  margin: 0;
  padding: 0;
}

body {
  font-family: "Inter";
  font-style: normal;
}

a {
  cursor: pointer;
}

.container {
  max-width: 737px;
  padding: 0 20px;
  margin: 0 auto;
}

@media only screen and (max-width: 690px) {
  .container {
    max-width: 690px;
  }
}
</style>
