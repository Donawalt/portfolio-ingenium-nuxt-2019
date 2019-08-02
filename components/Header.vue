<template>
  <section class="header">
    <NLink to="/" class="logo">INGENIVM</NLink>
    <ul class="menu">
      <li>
        <NLink to="/project" class="button">projects</NLink>
      </li>
      <li>
        <NLink to="/studio" class="button">studio</NLink>
      </li>
      <li>
        <NLink to="/contact" class="button">contact</NLink>
      </li>
    </ul>
  </section>
</template>

<style scoped>
a {
  color: white;
  text-decoration: none;
  transition: 250ms;
}
a:hover {
  text-decoration: underline;
  transition: 250ms;
}
.header {
  display: flex;
  justify-content: space-between;
  position: fixed;
  width: 100%;
  top: 0;
  padding: 10px;
  z-index: 1000;
}
.menu {
  display: flex;
  list-style: none;
}
.menu > li {
  margin-left: 6px;
}
.logo {
  font-weight: bold;
}
</style>
