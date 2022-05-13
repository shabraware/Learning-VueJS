<template>
  <h2>Component C</h2>
  <h3>name {{ name }}</h3>
  <h3>username {{ userName }}</h3>
  <h3>c_username {{ c_userName }}</h3>
  <h3>c_count {{ c_count }}</h3>
  <h3>c_heroname {{ c_heroName.firstName }} {{ c_heroName.lastName }}</h3>
  <button @click="increment">Child Increment</button>
</template>

<script>
import { inject } from 'vue';
export default {
  name: 'ChildC',
  setup() {
    const c_userName = inject('c_userName', 'DefaultName');
    const c_heroName = inject('c_heroName');
    const c_count = inject('c_count');
    const increment = inject('increment');
    return {
      c_userName,
      c_heroName,
      c_count,
      increment,
    };
  },
  data() {
    return {
      name: this.userName,
    };
  },
  inject: ['userName'],
};
</script>

<style></style>
