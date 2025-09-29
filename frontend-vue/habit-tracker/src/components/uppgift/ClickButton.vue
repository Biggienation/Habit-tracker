<script setup lang="ts">
import {ref} from 'vue'
const nr = ref(0);
const disable = ref(false);

function count (){
  if (nr.value < 5) {
    nr.value++
    return
  }
  disable.value = true
}

</script>

<template>
  <button @click="count" :class="{disabled: disable}">{{nr}}</button>
</template>

<style scoped>
.disabled{
  background-color: red;
}
</style>
