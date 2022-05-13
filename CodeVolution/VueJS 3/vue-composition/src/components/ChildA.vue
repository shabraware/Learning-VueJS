<template>
  <h2>Component A</h2>
  <ChildB />
</template>

<script>
import ChildB from './ChildB.vue';
export default {
  name: 'ChildA',
  components: {
    ChildB,
  },
};
</script>

<style></style>
