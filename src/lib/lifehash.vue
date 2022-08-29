<template lang="pug">
// a vue component wrapper for Lifehash icons <https://github.com/BlockchainCommons/lifehash.info>
img(:src="icon" :alt="input")
</template>

<script setup lang="ts">
import { ref, defineProps, onMounted, computed } from "vue";
import instantiate_lifehash from "./lifehash.js";
import { LifeHashModule } from "./lifehash";

// take a string as the input for the generator
const props = defineProps({
  input: String,
  // versions:
  // 0 - first version | 1 - recommended | 2 - recommended detailed | 3 - fiducial | 4 - fiducial monochrome
  version: {
    type: Number,
    default: 1,
  },
});

const lifehash = ref<LifeHashModule>();

const icon = computed(() => {
  if (!!lifehash.value) {
    let result = lifehash.value.makeFromUTF8(props.input!, props.version, 6);
    return result.src;
  }
});

// // run lifehash generator and return rendered image
// const renderIcon = async () => {
//
//   // render the image
//   let result = lifehash.makeFromUTF8(props.input, props.version, 6);
//   icon.value = result.src
// }
// async render
onMounted(async () => {
  lifehash.value = await instantiate_lifehash();
});
</script>
