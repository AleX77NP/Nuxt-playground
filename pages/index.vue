<template>
  <div>
    <AppHeader />
    <main>
      <nuxt-link style="text-decoration: none;" to="/posts">
        <button class="btn">View Posts</button>
      </nuxt-link>
    </main>
  </div>
</template>

<script>
export default {}
</script>

<style scoped>
.btn {
  width: 240px;
  height: 80px;
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

.btn:hover {
  transform: scale(0.97);
  opacity: 0.9;

}
</style>
