<template>
  <div>
    <button @click="incrementCounter">Clicked {{ counter }} times</button>
  </div>
</template>

<script>
import counterMixin from '../mixins/counter';
export default {
  name: 'ClickCounter',
  mixins: [counterMixin],
};
</script>

<style lang="scss" scoped></style>
