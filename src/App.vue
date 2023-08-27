<script setup>

import { VueElement, ref } from 'vue';
import Preview from './components/Preview.vue';
import Panel from './components/Panel.vue';

const options = ref([
  'default',
  'default',
  'default'
]);

function setOption(choice, option){
  options.value[choice - 1] = option;
}

</script>

<template>

  <Preview :options="options" />
  <Panel @optionSet="setOption"/>

</template>

<style scoped>
header {
  line-height: 1.5;
}

.logo {
  display: block;
  margin: 0 auto 2rem;
}

@media (min-width: 1024px) {
  header {
    display: flex;
    place-items: center;
    padding-right: calc(var(--section-gap) / 2);
  }

  .logo {
    margin: 0 2rem 0 0;
  }

  header .wrapper {
    display: flex;
    place-items: flex-start;
    flex-wrap: wrap;
  }
}
</style>
