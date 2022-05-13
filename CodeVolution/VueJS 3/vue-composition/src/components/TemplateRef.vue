<template>
  <div>
    <input type="text" ref="inputRef" />
    <input type="text" />
  </div>
</template>

<script>
import { onMounted, ref } from 'vue';
export default {
  setup() {
    const inputRef = ref(null);
    onMounted(() => {
      inputRef.value.focus();
    });
    return {
      inputRef,
    };
  },
  // mounted() {
  //   this.$refs.inputRef.focus();
  // },
};
</script>

<style></style>
