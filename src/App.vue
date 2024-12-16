<script setup lang="ts">
import { ref } from 'vue';
const elementId = ref(crypto.randomUUID())
const htmlContent = ref('<p>Hello world</p>');
const changeContent = () => {
  htmlContent.value = `<p>Value: ${crypto.randomUUID()}</p>`
}
const changeId = () => {
  elementId.value = crypto.randomUUID()
}
</script>

<template>
  <div v-html="htmlContent" v-bind:id="elementId"></div>
  <button @click="changeContent">Thay đổi content</button>
  <button @click="changeId">Thay đổi id</button>
</template>

<style scoped>
header {
  line-height: 1.5;
}

.logo {
  display: block;
  margin: 0 auto 2rem;
}

@media (min-width: 1024px) {
  header {
    display: flex;
    place-items: center;
    padding-right: calc(var(--section-gap) / 2);
  }

  .logo {
    margin: 0 2rem 0 0;
  }

  header .wrapper {
    display: flex;
    place-items: flex-start;
    flex-wrap: wrap;
  }
}
</style>
