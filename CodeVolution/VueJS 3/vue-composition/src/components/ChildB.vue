<template>
  <h2>Component B</h2>
  <ChildC />
</template>

<script>
import ChildC from './ChildC.vue';
export default {
  name: 'ChildB',
  components: {
    ChildC,
  },
};
</script>

<style></style>
