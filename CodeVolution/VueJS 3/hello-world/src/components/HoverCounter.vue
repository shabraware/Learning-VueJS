<template>
  <div>
    <h2 @mouseover="incrementCounter">Hovered {{ counter }} times</h2>
  </div>
</template>

<script>
import counterMixin from '../mixins/counter';
export default {
  name: 'HoverCounter',
  mixins: [counterMixin],
};
</script>

<style lang="scss" scoped></style>
