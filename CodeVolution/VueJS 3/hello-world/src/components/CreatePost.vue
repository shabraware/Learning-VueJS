<template>
  <form @submit.prevent="submitPostHandler">
    <div>
      <label for="userId">Post User Id</label>
      <input type="text" id="userId" v-model="formData.userId" />
    </div>
    <div>
      <label for="title">Post Title</label>
      <input type="text" id="title" v-model="formData.title" />
    </div>
    <div>
      <label for="body">Post Body</label>
      <input type="text" id="body" v-model="formData.body" />
    </div>
    <button>Submit</button>
  </form>
</template>

<script>
import axios from 'axios';
export default {
  name: 'CreatePost',
  data: function () {
    return {
      formData: {
        userId: '',
        title: '',
        body: '',
      },
    };
  },
  methods: {
    submitPostHandler: async function () {
      try {
        const response = await axios.post(
          'https://jsonplaceholder.typicode.com/posts',
          this.formData
        );
        console.log(response.data);
        this.formData.userId = '';
        this.formData.title = '';
        this.formData.body = '';
      } catch (error) {
        console.log(error);
      }
    },
  },
};
</script>

<style scoped></style>
