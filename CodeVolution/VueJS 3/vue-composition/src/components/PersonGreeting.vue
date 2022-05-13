<template>
  <div>Hello {{ fullName }}</div>
  <div>Hello {{ c_fullName }}</div>
  <button @click="setName">Set Name to Yousef Elshabrawy</button>
</template>

<script>
import { computed } from 'vue';
export default {
  name: 'PersonGreeting',
  props: {
    firstName: {
      type: String,
      required: true,
      default: 'Yousef',
    },
    lastName: {
      type: String,
      required: true,
      default: 'Elshabrawy',
    },
  },
  // props: ['firstName', 'lastName'],
  computed: {
    fullName() {
      return `${this.firstName} ${this.lastName}`;
    },
  },
  emits: ['setName'],
  methods: {
    // setName() {
    //   this.$emit('setName', 'Yousef', 'Elshabrawy');
    // },
  },
  setup(props, context) {
    const c_fullName = computed(() => `${props.firstName} ${props.lastName}`);
    function setName() {
      context.emit('setName', 'Yousef', 'Elshabrawy');
    }
    return {
      c_fullName,
      setName,
    };
  },
};
</script>

<style></style>
