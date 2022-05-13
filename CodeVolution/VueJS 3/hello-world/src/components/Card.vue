<template>
  <div class="card">
    <header id="card-header">
      <slot name="header" />
    </header>
    <div id="card-content">
      <slot>Fallback Card Content</slot>
      <slot>Fallback Card Content</slot>
    </div>
    <footer id="card-footer">
      <slot name="footer" />
    </footer>
  </div>
</template>

<script>
export default {
  // eslint-disable-next-line vue/multi-word-component-names
  name: 'Card',
};
</script>

<style scoped>
.card {
  text-align: center;
  padding: 30px;
  color: #333;
  height: 10rem;
  background-color: aqua;
}
</style>
