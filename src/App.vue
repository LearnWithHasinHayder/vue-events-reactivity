<script setup>
import { ref } from "vue"
const space = ref(0)
const message = ref("Hello Vue 3")

function spacePressed(){
  space.value++
  message.value = "Space Pressed " + space.value + " times"
}
</script>

<template>
  <section class="container mx-auto flex items-center flex-col">
    <h1 class="text-center text-2xl py-10">Events & Reactivity in Vue.js</h1>
    <h2 class="mt-10">{{ message }}</h2>
    <div class="container mx-auto flex space-x-5 justify-center m-5">
      <input type="text" name="" id="" class="border border-gray-500 bg-white p-5" @keyup.space="spacePressed()">
    </div>
  </section>
</template>

<style scoped></style>