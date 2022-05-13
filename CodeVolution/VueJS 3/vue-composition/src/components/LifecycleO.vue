<template>
  <div>Options API Lifecyle Hooks</div>
</template>

<script>
export default {
  name: 'LifeCycleO',
  beforeCreate() {
    console.log('LifecycleO beforeCreate()');
  },
  created() {
    console.log('LifecycleO created()');
  },
  beforeMount() {
    console.log('LifecycleO beforeMount()');
  },
  mounted() {
    console.log('LifecycleO mounted()');
  },
  beforeUpdate() {
    console.log('LifecycleO beforeUpdate()');
  },
  updated() {
    console.log('LifecycleO updated()');
  },
  beforeUnmount() {
    console.log('LifecycleO beforeUnmount()');
  },
  unmounted() {
    console.log('LifecycleO unmounted()');
  },
};
</script>

<style></style>
