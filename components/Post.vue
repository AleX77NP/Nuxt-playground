<template>
  <nuxt-link style="text-decoration: none;" :to="'posts/'+ id">
    <div class="post">
      <h5>{{ post.title}}</h5>
      <p>{{ post.body }}</p>
  </div>
  </nuxt-link>
</template>

<script>
export default {
  name: 'Post',
  props: ['post', 'id']
}
</script>

<style>
  .post  {
    border-radius: 20px;
    text-align: center;
    border: 2px solid skyblue;
    margin-bottom: 16px;
    cursor: pointer;
    padding: 0 16px;
  }
</style>
