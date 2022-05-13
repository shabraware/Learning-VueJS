<template>
  <h2>Options - {{ o_firstName }}</h2>
  <h2>Composition - {{ c_firstName }}</h2>
  <h2>Composition - {{ state.c_firstName }}</h2>
  <h2>Composition - {{ reactiveGreet }}</h2>
</template>

<script>
import { ref, reactive } from 'vue';
export default {
  name: 'Data',
  setup() {
    const c_firstName = ref('Yousef');
    const greet = `Hello ${c_firstName.value}`;
    const state = reactive({
      c_firstName: 'Yousef',
      c_lastName: 'Elshabrawy',
      c_heroName: 'Shabrawy',
    });
    const reactiveGreet = `Hello ${state.c_firstName}`;
    return {
      c_firstName,
      greet,
      state,
      reactiveGreet,
    };
  },
  data() {
    return {
      o_firstName: 'Yousef',
      o_lastName: 'Elshabrawy',
      o_heroName: 'Shabrawy',
    };
  },
};
</script>

<style></style>
