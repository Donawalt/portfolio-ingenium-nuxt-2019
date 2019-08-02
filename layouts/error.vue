<template>
  <div class="container">
    <h1 v-if="error.statusCode === 404">Page not found</h1>
    <h1 v-else>An error occurred</h1>
    <nuxt-link to="/">Home page</nuxt-link>
  </div>
</template>

<script>
export default {
  props: ['error'],
    head() {
      return {
        title: 'Error | INGENIVM PORTFOLIO'
      }
    },
}
</script>

<style scoped>
.container{
    display: flex;
    justify-content: center;
    align-items: center;
    height: 100vh;
    width: 100vw;
    flex-direction: column;
}

h1{
    font-size: 100px;
    margin-bottom: 20px;
    color: transparent;
    -webkit-text-stroke: 2px white;
}

a{
    color:white;
    text-decoration: none;
    background-color: darkslategrey;
    padding: 10px;
    border-radius: 8px;
}
</style>
