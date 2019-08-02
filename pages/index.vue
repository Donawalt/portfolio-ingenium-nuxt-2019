<template>
  <div ref="loader" class="Loader content">
    <div ref="loaderC" class="Loader__container">
      <section class="Loader__intro">
        <p ref="hey" class="intro_item intro__hey">Hey</p>
        <p ref="we" class="intro_item intro__we">We are</p>
      </section>
      <section class="Loader__title">
        <h1 ref="title" class="title__ingenivm">INGENIVM</h1>
      </section>
      <section class="Loader__loader">
        <p class="loader__num">
          <span ref="num">0</span>%
        </p>
      </section>
    </div>
    <div class="Loader__background">
      <img src="~/assets/backgroundLoader.jpg" alt>
    </div>
  </div>
</template>

<script>
import { TimelineLite } from "gsap";

export default {
  layout: "empty",
  methods: {
    onload: function() {
      const { loader, loaderC, hey, we, title, num } = this.$refs;
      const tl = new TimelineLite();
      let load = { value: 0 };
      let _this = this;

      tl.to(load, 5, {
        value: "+=100",
        roundProps: "value",
        onUpdate: updateHandler
      });
      tl.to(hey, 0.5, { x: 0 }, "-=4");
      tl.to(we, 0.5, { x: 0 }, "-=3");
      tl.to(title, 0.8, { y: 0, delay: 0.5 });
      tl.to(loaderC, 0.8, { backgroundColor: "rgba(0,0,0,.5)" }, "-=1");
      tl.to(title, 1.5, { color: "white" }, "-=1");
      tl.to(loader, 1, {
        opacity: 0,
        delay: 0.5
      });

      function updateHandler() {
        num.innerHTML = load.value;
        if (load.value === 100) {
          setTimeout(function() {
            _this.onComplete();
          }, 5000);
        }
      }
    },
    onComplete: function() {
      this.$router.push({ path: "project" });
    }
  },
  mounted: function() {
    this.onload();
  }
};
</script>

<style scoped>
.Loader {
  height: 100vh;
  width: 100vw;
  background-color: black;
  color: white;
  overflow: hidden;
}
.Loader__container {
  height: 100%;
  width: 100%;
  display: grid;
  grid-template-rows: 1fr 3fr 1fr;
  z-index: 2;
  position: absolute;
  background-color: rgb(0, 0, 0);
}
.Loader__intro {
  display: flex;
  flex-direction: column;
  text-align: left;
  font-weight: bold;
  font-size: 36px;
  line-height: 42px;
  padding-top: 10px;
  padding-left: 10px;
}
.Loader__title {
  display: flex;
  justify-content: center;
  align-items: center;
  font-weight: bold;
  font-size: 200px;
  line-height: 234px;
  color: transparent;
  -webkit-text-stroke: 2px rgb(255, 255, 255);
  overflow: hidden;
}
.Loader__loader {
  display: flex;
  justify-content: flex-end;
  align-items: flex-end;
  font-size: 26px;
  line-height: 30px;
  font-weight: bold;
  padding-bottom: 10px;
  padding-right: 10px;
}
.Loader__background {
  position: fixed;
  height: 100%;
  width: 100%;
  top: 0;
  z-index: 0;
  overflow: hidden;
  display: flex;
  justify-content: center;
  align-items: center;
}

.intro_item {
  transform: translate(-200px);
}

.title__ingenivm {
  transform: translate(0px, 100vh);
}
</style>
