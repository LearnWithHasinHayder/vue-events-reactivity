<script setup>
const location = "Dhaka"
const weather = "t"
</script>

<template>
  <section class="container mx-auto flex items-center flex-col">
    <h1 class="text-center text-2xl py-10">Events & Reactivity in Vue.js</h1>
    <div class="container mx-auto flex space-x-5 justify-center m-5">
      <button class="bg-blue-500 hover:bg-blue-700 text-white font-bold py-2 px-4 rounded">
        Button
      </button>
      <button class="bg-blue-500 hover:bg-blue-700 text-white font-bold py-2 px-4 rounded">
        Button
      </button>
    </div>
    <div class="w-1/3 bg-gray-200 p-10 flex items-center flex-col space-y-10">
      <h1 class="text-3xl">{{ location }}</h1>

      <template v-if="weather == 's'">
        <h2 class="text-2xl">Weather: Sunny</h2>
        <img class="w-32" src="https://creazilla-store.fra1.digitaloceanspaces.com/icons/7911203/weather-icon-md.png" alt="">
      </template>

      <template v-if="weather == 'pc'">
        <h2 class="text-2xl">Weather: Partly Cloudy</h2>
        <img class="w-32" src="https://creazilla-store.fra1.digitaloceanspaces.com/icons/7912718/weather-icon-md.png" alt="">
      </template>

      <template v-if="weather == 'r'">
        <h2 class="text-2xl">Weather: Rainy</h2>
        <img class="w-32" src="https://creazilla-store.fra1.digitaloceanspaces.com/icons/7913380/weather-icon-md.png" alt="">
      </template>

      <template v-if="weather == 't'">
        <h2 class="text-2xl">Weather: Thunderstorm</h2>
        <img class="w-32" src="https://creazilla-store.fra1.digitaloceanspaces.com/icons/7912589/weather-icon-md.png" alt="">
      </template>
    </div>
  </section>
</template>

<style scoped></style>