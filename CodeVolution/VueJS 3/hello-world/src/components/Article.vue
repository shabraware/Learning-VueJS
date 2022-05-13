<template>
  <div>
    <h2 v-bind="$attrs">{{ title }}</h2>
    <p v-bind="$attrs">{{ numberOfLikes }}</p>
  </div>
</template>

<script>
export default {
  // eslint-disable-next-line vue/multi-word-component-names
  name: 'Article',
  props: {
    title: { type: String, default: 'Title' },
    numberOfLikes: Number,
  },
  inheritAttrs: false,
};
</script>

<style scoped></style>
