<script setup>
import { ref, reactive } from 'vue'
//reactivity
const activeIndex = ref(0)
const accordions = reactive([
  {
    heading: "What is term?",
    content: "Lorem ipsum dolor sit, amet consectetur adipisicing elit. Sequi dolor dolorum odio, saepe quibusdam iusto possimus nesciunt dolores assumenda quae totam, doloremque odit. Itaque cum animi, labore debitis deserunt iusto!",
    isOpen:true,
  },
  {
    heading: "When to use Accordion Components?",
    content: "Lorem, ipsum dolor sit amet consectetur adipisicing elit. Ut suscipit itaque, sequi incidunt ab sit optio debitis dignissimos doloribus ratione nobis id mollitia maiores eveniet necessitatibus dolorum praesentium! Corrupti, at.",
    isOpen:false,
  },
  {
    heading: "How can it be defined?",
    content: "Lorem ipsum dolor sit amet consectetur adipisicing elit. Minima facilis labore voluptates provident nam, delectus suscipit nihil optio voluptate quae porro fugiat magni excepturi doloribus.",
    isOpen:false,
  },
  {
    heading: "Chamber reached do he nothing be?",
    content: "Lorem ipsum, dolor sit amet consectetur adipisicing elit. Ullam minima maiores magni dolore qui architecto pariatur incidunt repellat quos hic? Eius, eveniet accusantium! Quisquam, quo. Vitae ipsum ad veritatis commodi quasi expedita!",
    isOpen:false,
  }
])

// accordions[0].isOpen=true
</script>

<template>
  <section class="container mx-auto flex items-center flex-col">
    <h1 class="text-center text-2xl py-10">Events & Reactivity in Vue.js</h1>

    <div class="w-full p-10 bg-gradient-to-br from-pink-50 to-indigo-100 grid place-items-center">
      <div class="w-3/4 mx-auto rounded border">
        <div class="bg-white p-10 shadow-sm">
          <h3 class="text-lg font-medium text-gray-800">Several Windows stacked on each other</h3>
          <p class="text-sm font-light text-gray-600 my-3">
            The accordion is a graphical control element comprising a vertically stacked list of items such as labels or thumbnails
          </p>

          <div class="h-1 w-full mx-auto border-b my-5"></div>

          <!-- What is term -->
          <div class="transition hover:bg-indigo-50" v-for="(accordion,index) in accordions" :key="index" >
            <!-- header -->
            <div @click="activeIndex=index" class="accordion-header cursor-pointer transition flex space-x-5 px-5 items-center h-16" >
              <i class="fas" :class="index==activeIndex?'fa-minus':'fa-plus'"></i>
              <h3 >{{accordion.heading}}</h3>
            </div>
            <!-- Content -->
            <div class="px-5 pt-0 text-left pb-5" v-show="index==activeIndex"  >
              <p class="leading-6 font-light pl-9 ">
              {{ accordion.content }}
              </p>
            </div>
          </div>
        </div>
      </div>
    </div>

    <div class="w-full p-10 bg-gradient-to-br from-pink-50 to-indigo-100 grid place-items-center">
      <div class="w-3/4 mx-auto rounded border">
        <div class="bg-white p-10 shadow-sm">
          <h3 class="text-lg font-medium text-gray-800">Several Windows stacked on each other</h3>
          <p class="text-sm font-light text-gray-600 my-3">
            The accordion is a graphical control element comprising a vertically stacked list of items such as labels or thumbnails
          </p>

          <div class="h-1 w-full mx-auto border-b my-5"></div>

          <!-- What is term -->
          <div class="transition hover:bg-indigo-50" v-for="(accordion,index) in accordions" :key="index" >
            <!-- header -->
            <div @click="accordion.isOpen=!accordion.isOpen"  class="accordion-header cursor-pointer transition flex space-x-5 px-5 items-center h-16" >
              <i class="fas" :class="accordion.isOpen?'fa-minus':'fa-plus'"></i>
              <h3>{{accordion.heading}}</h3>
            </div>
            <!-- Content -->
            <div class="px-5 pt-0 text-left pb-5" v-show="true==accordion.isOpen" >
              <p class="leading-6 font-light pl-9 ">
              {{ accordion.content }}
              </p>
            </div>
          </div>
        </div>
      </div>
    </div>
    
  </section>
</template>

<style scoped></style>