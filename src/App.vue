<script setup>
import { ref } from "vue"
const about = ref("Hello")
const links=[
  {
    name: 'Google',
    url: "https://www.google.com",
    about:"Google is an American multinational technology company that specializes in Internet-related services and products, which include online advertising technologies, a search engine, cloud computing, software, and hardware."
  },
  {
    name: 'Microsoft',
    url: "https://www.microsoft.com",
    about:"Microsoft Corporation is an American multinational technology company with headquarters in Redmond, Washington. It develops, manufactures, licenses, supports, and sells computer software, consumer electronics, personal computers, and related services."
  },
  {
    name: 'Facebook',
    url: "https://www.facebook.com",
    about:"Facebook is an American online social media and social networking service based in Menlo Park, California, and a flagship service of the namesake company Facebook, Inc."
  },
  {
    name:"Twitter",
    url:"https://www.twitter.com",
    about:"Twitter is an American microblogging and social networking service on which users post and interact with messages known as tweets. Registered users can post, like and retweet tweets, but unregistered users can only read them."
  }
]

function setText(text){
  about.value=text
}
</script>

<template>
  <section class="container mx-auto flex items-center flex-col">
    <h1 class="text-center text-2xl py-10">Events & Reactivity in Vue.js</h1>
    <h2 class="mt-10">{{ about }}</h2>
    <div class="container mx-auto flex space-x-5 justify-center m-[1000px]">
      <a
        v-for="link in links"
        :key="link.name"
        href="#"
        @click.prevent="setText(link.about)"
        >{{ link.name }}</a
      >
    </div>
  </section>
</template>

<style scoped></style>