<script setup>
import { ref } from "vue"
const message = ref("Hello Vue 3")

const space = ref(0)

function spacePressed(){
  space.value++
  message.value = "Space pressed " + space.value + " times"
}

function pressedWhat(event){
  message.value = "You pressed " + event.key 
}

function buttonPressed(){
  message.value = "You clicked the button"
}

function ctrlRightClicked(){
  message.value = "Ctrl+Right Click"
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
        <h1 class="text-center text-2xl py-10">Assignment</h1>
        <p class="p-5">Make These Buttons Work</p>
        <div class="flex justify-between space-x-6">
            <div class="p-10 border w-96 flex flex-col space-y-5">
                <button class="bg-blue-500 hover:bg-blue-700 text-white font-bold py-2 px-4 rounded">
                    Light 1 On
                </button>
                <button class="bg-blue-500 hover:bg-blue-700 text-white font-bold py-2 px-4 rounded">
                    Light 2 On
                </button>
                <button class="bg-gray-500 hover:bg-gray-700 text-white font-bold py-2 px-4 rounded">
                    Light 3 Off
                </button>
            </div>
            <div class="p-10 border w-96 flex flex-col space-y-5">
                <img class="w-20" src="//img.icons8.com/?size=512&id=12244&format=png" alt="">
                <img class="w-20" src="//img.icons8.com/?size=512&id=12244&format=png" alt="">
                <img class="w-20" src="https://img.icons8.com/?size=512&id=75&format=png" alt="">
            </div>
        </div>
    </section>
</template>

<style scoped></style>