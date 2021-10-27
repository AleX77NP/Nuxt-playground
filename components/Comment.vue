<template>
  <nuxt-link style="text-decoration: none;" :to="'posts/'+ id">
    <div class="comment">
      <h5>{{ comment.email}}</h5>
      <p>Name: {{ comment.name }}</p>
      <p>{{ comment.body }}</p>
  </div>
  </nuxt-link>
</template>

<script>
export default {
  name: 'Comment',
  props: ['comment', 'id']
}
</script>

<style>
  .comment  {
    border-radius: 20px;
    text-align: center;
    border: 2px solid skyblue;
    margin-bottom: 16px;
    cursor: pointer;
    padding: 0 16px;
  }
</style>
