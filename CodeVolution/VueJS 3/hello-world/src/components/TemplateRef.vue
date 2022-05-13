<template>
  <div>
    <input type="text" ref="input" />
  </div>
</template>

<script>
export default {
  name: 'TemplateRef',
  mounted() {
    this.$refs.input.focus();
  },
};
</script>

<style scoped></style>
