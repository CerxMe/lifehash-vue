<template>
  <div>
    <LifeHash :input="input" />
    <input v-model="input">
  </div>
</template>

<script setup>
import { ref } from 'vue'
import LifeHash from '../../dist/lifehash-vue.js';
const input = ref('Hello World!');
</script>