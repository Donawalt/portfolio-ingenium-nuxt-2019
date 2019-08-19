<template>
  <div class="container">
    <h1>thanks for your message</h1>
    <nuxt-link to="/">Home page</nuxt-link>
  </div>
</template>

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
    font-size: 80px;
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
