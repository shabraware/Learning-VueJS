<template>
  <div>
    <input type="text" placeholder="Name" v-model="name" />
    <br />
    <input type="text" placeholder="First Name" v-model="firstName" />
    <input type="text" placeholder="Last Name" v-model="lastName" />
    <br />
    <input type="text" placeholder="First Name" v-model="fName" />
    <input type="text" placeholder="Last Name" v-model="lName" />
  </div>
</template>

<script>
import { ref, watch, reactive, toRefs } from 'vue';
export default {
  name: 'Watch',
  setup() {
    const firstName = ref('');
    const lastName = ref('Elshabrawy');
    watch([firstName, lastName], (newValues, oldValues) => {
      console.log(`The old first name is ${oldValues[0]}`);
      console.log(`The new first name is ${newValues[0]}`);
      console.log(`The old last name is ${oldValues[1]}`);
      console.log(`The new last name is ${newValues[1]}`);
    });

    const state = reactive({
      fName: '',
      lName: '',
    });
    watch(
      () => ({ ...state }),
      (newState, oldState) => {
        console.log(`The old first name is ${oldState.fName}`);
        console.log(`The new first name is ${newState.fName}`);
        console.log(`The old last name is ${oldState.lName}`);
        console.log(`The new last name is ${newState.lName}`);
      }
    );

    return {
      firstName,
      lastName,
      ...toRefs(state),
    };
  },
  data() {
    return {
      name: '',
    };
  },
  watch: {
    name(newName, oldName) {
      console.log(`The old name is ${oldName}`);
      console.log(`The new name is ${newName}`);
    },
  },
};
</script>

<style></style>
