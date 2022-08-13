<template lang="pug">
// a vue component wrapper for Lifehash icons <https://github.com/BlockchainCommons/lifehash.info>
img(:src="icon" :alt="input")
</template>

<script setup>
import {ref, onMounted} from "vue";
import instantiate_lifehash from './lifehash.js';

// take a string as the input for the generator
const props = defineProps({
  input: String,
  // versions:
  // 0 - first version | 1 - recommended | 2 - recommended detailed | 3 - fiducial | 4 - fiducial monochrome
  version: {
    type: Number,
    default: 1
  }
})

const icon = ref(null);

// run lifehash generator and return rendered image
const renderIcon = async () => {
  const lifehash = await instantiate_lifehash();
  // render the image
  let result = lifehash.makeFromUTF8(props.input, props.version, 6);
  icon.value = result.src
}
// async render
onMounted(() => {
  renderIcon();
})
</script>