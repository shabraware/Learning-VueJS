<template>
  <div>
    <h2>Popup</h2>
    <input type="text" v-model="name" />
    <button @click="$emit('close', name)">Close Popup</button>
  </div>
</template>

<script>
export default {
  // eslint-disable-next-line vue/multi-word-component-names
  name: 'Popup',
  emits: {
    close(name) {
      if (!name) return false;
      else return true;
    },
  },
  data() {
    return {
      name: '',
    };
  },
};
</script>

<style scoped></style>
