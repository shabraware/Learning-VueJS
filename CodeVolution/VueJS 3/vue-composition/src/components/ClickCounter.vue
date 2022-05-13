<template>
  <div>
    <button @click="incrementCount">Clicked {{ count }} times</button>
  </div>
</template>

<script>
// import counterMixin from '../mixins/counter.js';
import useCounter from '../composables/useCounter.js';

export default {
  name: 'ClickCounter',
  // mixins: [counterMixin],
  setup() {
    const { count, incrementCount } = useCounter();
    return {
      count,
      incrementCount,
    };
  },
};
</script>

<style></style>
