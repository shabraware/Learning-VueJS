<template>
  <h2>Parent Component {{ name }}</h2>
  <h2>Parent count {{ count }}</h2>
  <h2>Parent Hero Name {{ firstName }} {{ lastName }}</h2>
  <button @click="increment">Parent Increment</button>
  <ChildA />
</template>

<script>
import { provide, ref, reactive, toRefs } from 'vue';
import ChildA from './ChildA.vue';
export default {
  name: 'ProvideInject',
  setup() {
    provide('c_userName', 'Yousef');
    const count = ref(0);
    const state = reactive({
      firstName: 'Yousef',
      lastName: 'Atef',
    });
    provide('c_count', count);
    provide('c_heroName', state);
    function increment() {
      count.value++;
    }
    provide('increment', increment);
    return {
      count,
      ...toRefs(state),
      increment,
    };
  },
  components: {
    ChildA,
  },
  data() {
    return {
      name: 'Yousef',
    };
  },
  provide() {
    // use function syntax so that we can access `this`
    return {
      userName: this.name,
    };
  },
};
</script>

<style></style>
