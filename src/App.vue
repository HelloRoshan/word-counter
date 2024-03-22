<script setup>
import { ref, computed } from 'vue';

const textContainer = ref("");

const wordCount =  computed(() => {
  if (textContainer.value.length) {
    return textContainer.value.match(/[A-Za-z0-9]+/g).length;
  }
  return 0;
});

const characterCount = computed(() => {
  return textContainer.value.length
})

</script>

<template>
  <header>
  </header>

  <main class="mt-10 mr-6  ml-6">
    <textarea name="container" id="" class="w-full h-96 p-4 border-black border-solid border-2 rounded" v-model="textContainer">
    </textarea>
    <div class="border-black border-solid border-2 p-2 rounded">
      <span>{{ wordCount }} word{{wordCount > 1 ? "s " : " "}}</span>
      <span>{{ characterCount }} character{{characterCount > 1 ? "s" : ""}}</span>
    </div>
  </main>
</template>

<style scoped>
</style>
