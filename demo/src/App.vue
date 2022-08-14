<template>
  <div>
    <LifeHash :input="input" />
    <input v-model="input" @focus="$event.target.select()">
  </div>
</template>

<script setup>
import { ref } from 'vue'
import LifeHash from 'lifehash-vue';
const input = ref('Hello, world!');
</script>