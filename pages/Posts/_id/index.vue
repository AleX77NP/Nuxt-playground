<template>
  <div class="post-wrapper">
    <p>{{ id }}</p>
    <div v-if="post">
      <h1>{{ post.title}} </h1>
      <p>{{ post.body }}</p>
      <strong style="display: block; margin-bottom: 8px;"> User: {{ post.userId }}</strong>
      <p style="font-size:18px; font-weight: bold;">Comments</p>
      <Comment v-for="comment in comments" :key="comment.id" :comment="comment" />
    </div>
    <nuxt-link style="text-decoration:none;" to="/posts">
      <button>Go Back</button>
    </nuxt-link>
  </div>
</template>

<script>
import axios from 'axios'
import Comment from '../../../components/Comment.vue'
export default {
  components: { Comment },

  data() {
    return {
      id: 0,
      post: null,
      comments: []
    }
  },
  async created() {
    try {
      let id = this.$route.params.id
      const response = await axios.get(`https://jsonplaceholder.typicode.com/posts/${id}`);
      console.log(response.data)
      this.post = response.data
      this.id = id
      const commentsRes = await axios.get(`https://jsonplaceholder.typicode.com/comments?postId=${id}`)
      this.comments = commentsRes.data

    }
    catch(e) {
      console.log(e)
    }
  }

}
</script>

<style>
.post-wrapper {
  width: 1000px;
  max-width: 95%;
  border-radius: 20px;
  border: 2px solid skyblue;
  padding: 8px 16px;
  margin: auto;
}

p {
  text-align: center;
}

button {
  width: 120px;
  height: 40px;
  font-size: 18px;
  font-weight: bold;
  outline: none;
  background-color: yellowgreen;
  color: white;
  border-radius: 20px;
  border: none;
  display: block;
  margin: 50px auto;
  cursor: pointer;
}
</style>
