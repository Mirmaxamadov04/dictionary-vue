<template>
  <div class="container">
    <div class="content__top">
      <div class="word">
        <h1 class="word__name">{{ word.word }}</h1>
        <p class="word__read">{{ word.phonetic }}</p>
      </div>

      <button class="audio-button" @click="audioPlay">
        <img
          src="@/images/image.svg"
          alt="no image"
          class="audio-button__image"
          width="21"
          height="21"
        />
      </button>
    </div>
  </div>
</template>

<script setup>
const props = defineProps(["word"]);

function audioPlay() {
  const audio = new Audio();
  props.word.phonetics.forEach((phonetic) => {
    if (phonetic.audio) {
      audio.src = phonetic.audio;
    }
  });

  audio.play();
}
</script>

<style>
.content__top {
  margin-top: 45px;
  display: flex;
  justify-content: space-between;
}

.word__name {
  font-weight: 700;
  font-size: 64px;
  line-height: 77px;
  color: #2d2d2d;
}

.word__read {
  padding-top: 8px;
  font-weight: 400;
  font-size: 24px;
  line-height: 29px;
  color: #a445ed;
  display: block !important;
}

.audio-button {
  width: 75px;
  height: 75px;
  padding: 20px;
  padding-left: 25px;
  margin-top: 20px;
  border-radius: 50px;
  justify-content: center;
  background: transparent;
  border: none;
  transition: 0.3s all ease;
  background: #a445ed;
  mix-blend-mode: normal;
  opacity: 0.9;
  cursor: pointer;
}

/*.audio-button:hover {
  background: #a445ed;
  opacity: 1;
}

.audio-button__image path {
  fill: #a445ed;
} */
</style>
