<template>
  <h2>Hello {{ heroName }}</h2>
</template>
<script>
export default {
  // eslint-disable-next-line vue/multi-word-component-names
  name: 'Greet',
  props: ['heroName'],
};
</script>
