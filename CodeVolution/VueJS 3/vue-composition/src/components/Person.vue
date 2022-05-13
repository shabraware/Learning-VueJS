<template>
  <div>
    <input type="text" placeholder="First Name" v-model="firstName" />
    <input type="text" placeholder="Last Name" v-model="lastName" />
  </div>
  <person-greeting
    :firstName="firstName"
    :lastName="lastName"
    @setName="setNameChangeHandler"
  />
</template>

<script>
import { ref } from 'vue';
import PersonGreeting from './PersonGreeting.vue';
export default {
  name: 'Person',
  components: {
    'person-greeting': PersonGreeting,
    // PersonGreeting,
  },
  setup() {
    let firstName = ref('');
    let lastName = ref('');
    function setNameChangeHandler(fname, lname) {
      firstName.value = fname;
      lastName.value = lname;
    }
    return {
      firstName,
      lastName,
      setNameChangeHandler,
    };
  },
  data() {
    return {
      // firstName: '',
      // lastName: '',
    };
  },
};
</script>

<style></style>
