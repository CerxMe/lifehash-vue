# lifehash-vue
Wrapper component for [LifeHash](https://github.com/BlockchainCommons/lifehash.info) powered [identicons](https://en.wikipedia.org/wiki/Identicon) in Vue.js


## Installation
```
npm i lifehash-vue --save
```

## Usage
The default export is a Vue component that can be used in a Vue template.
```vue
<template>
  <div>
    <LifeHash input="Hello World!" />
  </div>
</template>

<script setup>
import LifeHash from 'lifehash-vue';
</script>
```
See the demo directory for a [working live example](https://leafy-raindrop-966db2.netlify.app).

### Props
Following props are available:

| Name | Type | Description |
| ---- | ---- | ----------- |
| input | String | The input string to hash |
| version | Number | The version of LifeHash to use (Default: 1) |

## Example results
| Version | Description           | Samples                                |
|---------|-----------------------|---------------------------------------|
| 0       | Version 1             | ![0](samples/version1.jpeg)           | 
| 1       | Version 2             | ![1](samples/version2.jpeg)           | 
| 2       | Version 2 - Detailed  | ![2](samples/detailed.jpeg)           | 
| 3       | Fiducial              | ![3](samples/fiducial.jpeg)           | 
| 4       | Fiducial - Monochrome | ![4](samples/grayscale-fiducial.jpeg) |
