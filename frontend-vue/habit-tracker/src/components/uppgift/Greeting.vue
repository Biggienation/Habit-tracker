<script setup lang="ts">
import {ref} from 'vue'
const name = ref('');
const greeting = ref('');

function onSubmit() {
  greeting.value = 'good morning ' + name.value;
  name.value = '';
}

</script>

<template>
  <h1 v-if="greeting">{{greeting}}</h1>
  <form @submit.prevent="onSubmit">
    <label>Name</label>
    <input type="text" v-model="name" placeholder="Name" />
  </form>

</template>

<style scoped>

</style>
