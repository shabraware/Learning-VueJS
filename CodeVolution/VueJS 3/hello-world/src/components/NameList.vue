<template>
  <div>
    <h3 v-for="name in names" :key="name.firstName">
      <slot :firstName="name.firstName" :lastName="name.lastName"></slot>
    </h3>
  </div>
</template>

<script>
export default {
  name: 'NameList',
  data: function () {
    return {
      names: [
        {
          firstName: 'Yousef',
          lastName: 'Atef',
        },
        {
          firstName: 'Yousef',
          lastName: 'Elmahdy',
        },
        {
          firstName: 'Ahmed',
          lastName: 'Nossir',
        },
      ],
    };
  },
};
</script>

<style scoped></style>
