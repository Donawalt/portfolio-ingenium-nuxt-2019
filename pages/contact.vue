<template>
  <div class="container">
    <section class="tag">
      <p class="we">
        <span ref="a">CONTACT</span>
      </p>
      <p class="a">
        <a ref="b" href="mailto:ingenium2100@gmail.com">ingenium2100@gmail.com</a>
      </p>
    </section>
  </div>
</template>

<script>
export default {};
</script>

<style scoped>
.tag,
.container {
  display: flex;
  flex-direction: column;
  justify-content: center;
  height: 50vh;
  width: 70vw;
  font-weight: bold;
}

.container {
  display: flex;
  align-items: center;
  align-content: center;
  justify-items: center;
  justify-content: center;
  width: 100vw;
  height: 100vh;
}

.tag > .we {
  font-size: 70px;
  color: transparent;
  -webkit-text-stroke: 2px white;
  overflow: hidden;
}

.a {
  display: flex;
  justify-content: center;
  align-items: center;
  font-size: 72px;
}
.a > a {
  color: white;
  text-decoration: none;
}
</style>
