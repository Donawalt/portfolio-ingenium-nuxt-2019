<template>
  <div class="container content">
    <section class="tag">
      <p class="we">
        <span ref="a">AUDIOVISUAL STUDIO</span>
      </p>
      <div class="team">
        <p class="a">
          <span>
            🖌
            <a ref="b" href="https://www.instagram.com/ehtomite/" target="_blanck">@EHTOMITE</a>
            to drawing
          </span>
        </p>
        <p class="a">
          🔊
          <a ref="b" href="https://www.instagram.com/le_moundele/" target="_blanck">@LE_MOUNDELE</a>
          to music
        </p>
        <p class="a">
          📽
          <a ref="b" href="https://www.instagram.com/bnjmn_ae/" target="_blanck">@BNJMN_AE</a>
          during editing
        </p>
      </div>
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
      enter(el){
        const tlE = new TimelineLite();

        tlE.to(el,1,{opacity: 1});
      },
      beforeLeave(el) {
        console.log('Before leave');
        el.style.opacity = 1;
      },
      leave(el){
        const tlE = new TimelineLite();

        tlE.to(el,1,{opacity: 0});
      }
    }
};
</script>

<style scoped>
.container {
  min-height: 100vh;
  display: flex;
  justify-content: center;
  align-items: center;
  text-align: center;
  font-weight: bold;
  text-align: left;
}
.we {
  font-size: 72px;
}
.team {
  font-size: 60px;
  text-transform: uppercase;
  padding-top: 10px;
  padding-bottom: 10px;
}

a {
  color: transparent;
  -webkit-text-stroke: 2px white;
  overflow: hidden;
  text-decoration: none;
  transition: 500ms;
}
a:hover {
  color: white;
  transition: 500ms;
}
</style>
