<script setup>
import { ref } from "vue"
const space = ref(0)
const message = ref("Hello Vue 3")

function spacePressed() {
  space.value++
  message.value = "Space Pressed " + space.value + " times"
}
</script>

<template>
  <section class="container mx-auto flex items-center flex-col">
    <h1 class="text-center text-2xl py-10">Events & Reactivity in Vue.js</h1>
    <h2 class="mt-10">{{ message }}</h2>
    <form action="https://google.com/search">
      <div class="container mx-auto flex space-x-5 justify-center m-5">
        <input name="q" type="text" id="" class="border border-gray-500 bg-white p-5" @keyup.space="spacePressed()">
      </div>

      <button class="bg-blue-500 hover:bg-blue-700 text-white font-bold py-2 px-4 rounded" @click="message = 'You searched for Horses'">
        Button
      </button>

    </form>
  </section>
</template>

<style scoped></style>