<template>
  <input type="text" placeholder="FName" v-model="fname" />
  <input type="text" placeholder="LName" v-model="lname" />

  <input type="text" placeholder="Hero Name" v-model="heroName" />
  <input type="text" placeholder="First Name" v-model="firstName" />
  <input type="text" placeholder="Last Name" v-model="lastName" />
</template>

<script>
import { ref, reactive, toRefs } from 'vue';

export default {
  name: 'VModel',
  setup() {
    const heroName = ref('');
    const state = reactive({
      firstName: '',
      lastName: '',
    });
    return {
      heroName,
      ...toRefs(state),
    };
  },
  data() {
    return {
      fname: '',
      lname: '',
    };
  },
};
</script>

<style></style>
