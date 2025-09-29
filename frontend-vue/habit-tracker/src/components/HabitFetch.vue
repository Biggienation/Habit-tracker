<script setup lang="ts">
import {ref} from "vue";

const container = ref<HTMLElement | null>(null);

 fetch("/habits.json").then((res) => res.json()).then((data) => {
   data.forEach((habit: any) => {
     const habitArticle = document.createElement('article');
     habitArticle.id = habit.id;

     habitArticle.innerHTML = `
     <p>${habit.category}</p>
     <p>${habit.progress}</p>
     <p>${habit.total}</p>
     `;

     container.value?.appendChild(habitArticle);
   });

 }).catch((error) => {
   console.log(error);
 })
</script>

<template>
  <section ref="container">

  </section>

</template>

<style scoped>

article{
  background-color: lightgray;
  display: flex;
  flex-direction: row;
}

section{
  background-color: lightgray;
}

</style>
