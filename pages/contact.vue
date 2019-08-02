<template>
  <div class="container content">
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
  export default {
    transition: {
      name: 'page',
      beforeEnter(el) {
        el.style.opacity = 0;
      },
      enter(el) {
        const tlE = new TimelineLite();

        tlE.to(el, 1, {
          opacity: 1
        });
      },
      beforeLeave(el) {
        console.log('Before leave');
        el.style.opacity = 1;
      },
      leave(el) {
        const tlE = new TimelineLite();

        tlE.to(el, 1, {
          opacity: 0
        });
      }
    },
    head() {
      return {
        title: 'Contact | INGENIVM PORTFOLIO'
      }
    }
  };

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

  .tag>.we {
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

  .a>a {
    color: white;
    text-decoration: none;
  }

</style>
