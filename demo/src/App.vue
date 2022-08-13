<template>
  <div>
    <LifeHash :input="input" />
    <input v-model="input">
  </div>
</template>

<script setup>
import { ref } from 'vue'
import LifeHash from 'lifehash-vue';
const input = ref('Hello World!');
</script>