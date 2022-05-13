<template>
  <input type="text" placeholder="FName" v-model="fname" />
  <input type="text" placeholder="LName" v-model="lname" />
  <h2>Options Fullname is {{ fullName }}</h2>

  <input type="text" placeholder="Ref First Name" v-model="refFirstName" />
  <input type="text" placeholder="Ref Last Name" v-model="refLastName" />
  <h2>Composition Ref Fullname is {{ refFullname }}</h2>

  <input
    type="text"
    placeholder="Reactive First Name"
    v-model="reactiveFirstName"
  />
  <input
    type="text"
    placeholder="Reactive Last Name"
    v-model="reactiveLastName"
  />
  <h2>Composition Reactive Fullname is {{ reactiveFullname }}</h2>
</template>

<script>
import { ref, computed, reactive, toRefs } from 'vue';

export default {
  name: 'Computed',
  setup() {
    const refFirstName = ref('');
    const refLastName = ref('');
    const refFullname = computed(
      () => `${refFirstName.value} ${refLastName.value}`
    );
    const state = reactive({
      reactiveFirstName: '',
      reactiveLastName: '',
    });
    const reactiveFullname = computed(
      () => `${state.reactiveFirstName} ${state.reactiveLastName}`
    );
    return {
      refFirstName,
      refLastName,
      refFullname,
      ...toRefs(state),
      reactiveFullname,
    };
  },
  data() {
    return {
      fname: '',
      lname: '',
    };
  },
  computed: {
    fullName() {
      return `${this.fname} ${this.lname}`;
    },
  },
};
</script>

<style></style>
