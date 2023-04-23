<template>
  <div class="container">
    <div class="content-main">
      <p class="word-type">{{ props.meanings.partOfSpeech }}</p>
      <p class="meaning">meaning</p>
      <ul>
        <li v-for="definition in props.meanings.definitions">
          <p class="definition">{{ definition.definition }}</p>
          <p class="example">{{ definition.example }}</p>
        </li>
      </ul>
      <p class="synonyms-paragraph" v-if="props.meanings.synonyms.length != 0">
        synonyms
      </p>
      <p
        class="synonyms"
        v-if="props.meanings.synonyms.length != 0"
        v-for="synonym in props.meanings.synonyms"
      >
        {{ synonym }}
      </p>
      <p class="synonyms-paragraph" v-if="props.meanings.antonyms.length != 0">
        antonyms
      </p>
      <p
        class="synonyms"
        v-if="props.meanings.antonyms.length != 0"
        v-for="antonym in props.meanings.antonyms"
      >
        {{ antonym }}
      </p>
    </div>
  </div>
</template>

<script setup>
const props = defineProps(["meanings"]);
console.log(props.meanings);
</script>

<style>
.word-type {
  margin-top: 40px;
  font-family: "Inter";
  font-style: italic;
  font-weight: 700;
  font-size: 24px;
  line-height: 29px;
  color: #2d2d2d;
}

.meaning {
  margin-top: 40px;
  font-family: "Inter";
  font-style: normal;
  font-weight: 400;
  font-size: 20px;
  line-height: 24px;
  color: #757575;
}

.definition {
  margin-top: 15px;
  margin-bottom: 15px;
  margin-left: 10px;
  font-family: "Inter";
  font-style: normal;
  font-weight: 400;
  font-size: 18px;
  line-height: 24px;
  color: #2d2d2d;
}

.example {
  margin-bottom: 15px;
  margin-left: 10px;
  font-family: "Inter";
  font-style: normal;
  font-weight: 400;
  font-size: 18px;
  line-height: 24px;
  color: #757575;
}

.synonyms {
  display: inline-block;

  margin-left: 30px;
  font-family: "Lora";
  font-style: normal;
  font-weight: 700;
  font-size: 20px;
  line-height: 26px;
  color: #a445ed;
}

.synonyms-paragraph {
  margin-top: 10px;
  margin-bottom: 10px;
  font-family: "Lora";
  font-style: normal;
  font-weight: 400;
  font-size: 20px;
  line-height: 26px;
  color: #757575;
}

ul {
  list-style: disc; /* Use a bullet point for the list item marker */
  color: #a445ed;
  margin-left: 35px;
}

.definition {
  color: black;
}
</style>
