<template>
  <div>
    <h2>{{ name }}</h2>
    <button v-on:click="setName">Change Name</button>
    <h2>{{ count }}</h2>
    <button @click="increamentCount">Increament</button>
    <h2>{{ first }} {{ last }}</h2>
    <button @click="changeLast">Change last</button>
  </div>
</template>

<script>
import { ref, reactive, toRefs } from 'vue';
export default {
  name: 'Methods',
  setup() {
    const count = ref(0);
    const state = reactive({
      first: 'Yousef',
      last: 'Atef',
    });
    function increamentCount() {
      count.value++;
    }
    function changeLast() {
      state.last = 'Elshabrawy';
    }
    return {
      count,
      increamentCount,
      ...toRefs(state),
      changeLast,
    };
  },
  data() {
    return {
      name: 'Yousef',
    };
  },
  methods: {
    setName() {
      this.name = 'Shabrawy';
    },
  },
};
</script>

<style></style>
