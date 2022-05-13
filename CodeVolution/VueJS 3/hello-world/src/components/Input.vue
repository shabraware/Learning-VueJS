<template>
  <input
    type="text"
    :value="modelValue"
    @input="$emit('update:modelValue', $event.target.value)"
  />
</template>

<script>
export default {
  // eslint-disable-next-line vue/multi-word-component-names
  name: 'Input',
  props: { modelValue: String },
  emits: ['update:modelValue'],
  data() {
    return {};
  },
};
</script>

<style scoped></style>
