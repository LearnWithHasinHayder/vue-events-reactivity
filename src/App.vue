<script setup>
import { ref } from "vue"
const space = ref(0)
const message = ref("Hello Vue 3")

function spacePressed() {
  space.value++
  message.value = "Space Pressed " + space.value + " times"
}

function pressedWhat(event) {
  message.value = "You pressed " + event.key
}

function divClicked(){
  alert("Div Clicked")
}

function buttonClicked(){
  alert("Button Clicked")
}
</script>

<template>
  <section class="container mx-auto flex items-center flex-col">
    <h1 class="text-center text-2xl py-10">Events & Reactivity in Vue.js</h1>
    <h2 class="mt-10">{{ message }}</h2>
    <form action="https://google.com/search">
      <div class="container mx-auto flex space-x-5 justify-center m-5">
        <input name="q" type="text"  class="border border-gray-500 bg-white p-5" @keyup.space="spacePressed()" placeholder="Press Space">
      </div>
      
      <div class="container mx-auto flex space-x-5 justify-center m-5">
        <input name="text" type="text" class="border border-gray-500 bg-white p-5" @keyup="pressedWhat($event)" placeholder="Type Something">
      </div>

      <button class="bg-blue-500 hover:bg-blue-700 text-white font-bold py-2 px-4 rounded" @click="message = 'You searched for Horses'">
        Button
      </button>

      <button class="bg-blue-500 ml-5 hover:bg-blue-700 text-white font-bold py-2 px-4 rounded" @click="message = 'Ctrl + Right Click'">
        Ctrol + Right Click
      </button>

    </form>

    <div class="bg-gray-200 w-[500px] h-80 mt-5 flex items-center justify-center" @click="divClicked()">
      <button class="bg-orange-500 hover:bg-orange-700 text-white font-bold py-2 px-4 rounded" @click="buttonClicked()" >
        Button
      </button>
    </div>
  </section>
</template>

<style scoped></style>