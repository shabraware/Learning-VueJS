<template>
  <div>
    <button @click="loadPostsHandler">Load Posts</button>
    <div v-for="post in posts" :key="post.id">
      <h3>UserId {{ post.userId }}</h3>
      <h2>Title {{ post.title }}</h2>
      <p>Body {{ post.body }}</p>
    </div>
  </div>
</template>

<script>
import axios from 'axios';
export default {
  name: 'PostsList',
  data: function () {
    return {
      posts: [],
    };
  },
  methods: {
    loadPostsHandler: function () {
      axios
        .get('https://jsonplaceholder.typicode.com/posts')
        .then((response) => {
          this.posts = response.data;
        })
        .catch((error) => {
          console.log(error);
        });
    },
  },
  mounted() {
    console.log(this);
  },
};
</script>

<style scoped>
div {
  border-bottom: 1px solid #000;
}
</style>
