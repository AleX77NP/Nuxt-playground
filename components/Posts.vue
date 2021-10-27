<template>
  <div class="container">
    <nuxt-link style="display: block; margin-bottom: 8px;" to="/">Go back</nuxt-link>
    <Post v-for="post in posts" :key="post.id" :id="post.id" :post="post" />
  </div>
</template>

<script>
import axios from 'axios'
import Post from './Post.vue'
export default {
  components: {
    Post
  },
  data() {
    return {
      posts: []
    }
  },
  async created() {
    try {
      const response = await axios.get('https://jsonplaceholder.typicode.com/posts');
      console.log(response.data)
      this.posts = response.data
    }
    catch(e) {
      console.log(e)
    }

  }
}
</script>

<style>
.container {
  padding: 0 20px;
  width: 1000px;
  max-width: 95%;
  margin: 0 auto;
  position: relative;
}
</style>
