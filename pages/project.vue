<template>
  <div>
    <div class="project">
      <section class="tag">
        <p class="we">
          <span ref="a">WE ARE</span>
        </p>
        <p class="a">
          <span ref="b">A VISUAL AND</span>
        </p>
        <p class="a">
          <span ref="c">SOUND DESIGN</span>
        </p>
        <p class="a">
          <span ref="e">STUDIO</span>
        </p>
      </section>
    </div>
    <div class="portfolio">
      <section class="project__item">
        <div class="picture"></div>
        <div class="title"></div>
      </section>
      <section class="project__item">
        <div class="picture"></div>
        <div class="title"></div>
      </section>
      <section class="project__item">
        <div class="picture"></div>
        <div class="title"></div>
      </section>
      <section class="project__item">
        <div class="picture"></div>
        <div class="title"></div>
      </section>
      <section class="project__item">
        <div class="picture"></div>
        <div class="title"></div>
      </section>
      <section class="project__item">
        <div class="picture"></div>
        <div class="title"></div>
      </section>
      <section class="project__item">
        <div class="picture"></div>
        <div class="title"></div>
      </section>
      <section class="project__item">
        <div class="picture"></div>
        <div class="title"></div>
      </section>
      <section class="project__item">
        <div class="picture"></div>
        <div class="title"></div>
      </section>
      <section class="project__item">
        <div class="picture"></div>
        <div class="title"></div>
      </section>
    </div>
  </div>
</template>

<script>
import { TimelineLite } from "gsap";

export default {
  methods: {
    onLoad: function() {
      const { a, b, c, e } = this.$refs;

      const tl1 = new TimelineLite();

      tl1.to(a, 0.3, { y: 0, rotation: 0 });
      tl1.to(b, 0.4, { y: 0, delay: 0.2, rotation: 0 });
      tl1.to(c, 0.3, { y: 0, rotation: 0 });
      tl1.to(e, 0.4, { y: 0, rotation: 0 });
    }
  },
  mounted: function() {
    this.onLoad();
  }
};
</script>

<style scoped>
.project {
  display: flex;
  justify-content: center;
  align-items: center;
  align-content: center;
  justify-items: center;
  height: 100vh;
}

.project__item {
  height: 50vh;
}
.tag {
  display: flex;
  flex-direction: column;
  justify-content: center;
  height: 50vh;
  width: 70vw;
  font-weight: bold;
}

.tag > .we {
  font-size: 70px;
  color: transparent;
  -webkit-text-stroke: 2px white;
  overflow: hidden;
}

.tag > .a {
  font-size: 80px;
  -webkit-text-stroke: 2px white;
  overflow: hidden;
}

.tag span {
  transform: translateY(350%) rotate(25deg);
  position: relative;
  display: block;
}

.portfolio {
  min-height: 100vh;
}
</style>
