<template>
  <div class="content">
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
        <div class="picture">
          <img src="~/assets/project-img/SECTRA-min.jpg" alt="SECTRA COVER" class="picture__item picture__img" />
        </div>
        <div class="title">
          <p>SECTRA</p>
        </div>
      </section>
      <section class="project__item">
        <div class="picture">
          <!-- <video controls autoplay muted loop></video> -->
          <img src="~/assets/project-img/REVERSE-min.jpg" alt="REVERSE COVER" class="picture__item picture__img" />
        </div>
        <div class="title">
          <p>REVERSE</p>
        </div>
      </section>
      <section class="project__item">
        <div class="picture">
          <video class="picture__item picture__vid" src="~/assets/project-vid/THE-MISPELING.mp4" loop autoplay
            muted></video>
        </div>
        <div class="title">
          <p>THE MISPELING</p>
        </div>
      </section>
      <section class="project__item">
        <div class="picture">
          <img src="~/assets/project-img/REVERSE2-min.jpg" alt="REVERSE COVER" class="picture__item picture__img" />
        </div>
        <div class="title">
          <p>REVERSE-2</p>
        </div>
      </section>
      <section class="project__item">
        <div class="picture">
          <img src="~/assets/project-img/CAGOULE-min.jpg" alt="REVERSE COVER" class="picture__item picture__img" />
        </div>
        <div class="title">CAGOULE</div>
      </section>
      <section class="project__item">
        <div class="picture">
          <video class="picture__item picture__vid" src="~/assets/project-vid/VNKNOWN-SMILE.mp4" loop autoplay
            muted></video>
        </div>
        <div class="title">
          <p>VNKNOWN</p>
        </div>
      </section>
      <section class="project__item">
        <div class="picture">
          <img src="~/assets/project-img/GUEPE-min.jpg" alt="REVERSE COVER" class="picture__item picture__img" />
        </div>
        <div class="title">
          <p>GUEPE</p>
        </div>
      </section>
      <section class="project__item">
        <div class="picture">
          <img src="~/assets/project-img/LEVEL1-min.jpg" alt="REVERSE COVER" class="picture__item picture__img" />
        </div>
        <div class="title">LEVEL 1</div>
      </section>
      <section class="project__item">
        <div class="picture">
          <video class="picture__item picture__vid" src="~/assets/project-vid/INTRO.mp4" loop autoplay muted></video>
        </div>
        <div class="title">
          <p>INTRO</p>
        </div>
      </section>
    </div>
    <div class="project__footer">
      <p class="project__footer-title">LET'S TALK</p>
      <hr class="project__footer-separator"/>
      <div class="project__footer-contact">
        <div class="footer-contact-item">
          <p class="contact-item_title">MAIL</p>
          <a href="mailto:ingenium2100@gmail.com">ingenium2100@gmail.com</a>
        </div>
        <div class="footer-contact-item">
          <p class="contact-item_title">THE TEAM</p>
          <ul>
            <li><a href="https://instagram.com/ehtomite">@EHTOMITE</a></li>
            <li><a href="https://instagram.com/le_moundele">@LE_MOUNDELE</a></li>
            <li><a href="https://instagram.com/bnjmn_ae">@BNJMN_AE</a></li>
          </ul>
        </div>
      </div>
      <center>
        <small>website design and code by <a href="https://donaelwalter.com/" target="_blanck">Donaël Walter</a></small>
      </center>
    </div>
  </div>
</template>

<script>
  import {
    TimelineLite
  } from "gsap";

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
    },
    created() {
      if (process.browser) {
        let smoothS = document.createElement('script')
        smoothS.setAttribute('src', '/js/smoothS.js');
        smoothS.setAttribute('defer', '');
        document.body.appendChild(smoothS)

      }
    },
    methods: {
      onLoad: function () {
        const {
          a,
          b,
          c,
          e
        } = this.$refs;

        const tl1 = new TimelineLite();

        tl1.to(a, 0.3, {
          y: 0,
          rotation: 0
        });
        tl1.to(b, 0.4, {
          y: 0,
          delay: 0.2,
          rotation: 0
        });
        tl1.to(c, 0.3, {
          y: 0,
          rotation: 0
        });
        tl1.to(e, 0.4, {
          y: 0,
          rotation: 0
        });
      }
    },
    mounted: function () {
      this.onLoad();
      var videos = document.querySelectorAll('video');

      if (videos === undefined) {
        alert('undefined');
      } else {
        for (let c = 0; c < videos.length; c++) {
          videos[c].addEventListener("mouseenter", e => {
            videos[c].muted = false;
            videos[c].play();
          });

          videos[c].addEventListener("mouseleave", e => {
            videos[c].muted = true;
          });
        }
      }
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
    height: 80vh;
  }

  .tag {
    display: flex;
    flex-direction: column;
    justify-content: center;
    height: 50vh;
    width: 70vw;
    font-weight: bold;
  }

  .tag>.we {
    font-size: 70px;
    color: transparent;
    -webkit-text-stroke: 2px white;
    overflow: hidden;
  }

  .tag>.a {
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


  .project__item {
    height: 60vh;
    display: grid;
    grid-template-columns: 2fr 2fr;
  }

  .project__item:nth-child(even) .title {
    grid-row: 1;
  }

  .portfolio .picture .picture__img {
    height: 400px;
    width: 400px;
  }

  .portfolio .picture .picture__vid {
    height: 400px;
    width: auto;
  }

  .portfolio .picture {
    display: flex;
    justify-content: center;
    align-items: center;
    flex-direction: row;
  }

  .portfolio .title {
    font-size: 50px;
    font-weight: bold;
    text-transform: uppercase;
    display: flex;
    justify-content: center;
    align-items: center;
  }

  a{
    color:white;
    text-decoration: none;
    transition: 500ms;
  }

  a:hover {
    color: transparent;
    -webkit-text-stroke: 1px darkturquoise;
    transition: 500ms;
  }

  .project__footer{
    height: 80vh;
    display: flex;
    flex-direction: column;
    justify-content: flex-end;
    padding: 15px;
  }

  .project__footer-title{
    font-size: 150px;
    font-weight: bold;
    color: transparent;
    -webkit-text-stroke: 2px white;
  }

  .project__footer-separator{
    border: none;
    background-color: white;
    height: 4px;
    width: 100%;
  }

  .project__footer-contact{
    display: flex;
  }
  .footer-contact-item{
    margin-right: 30px;
  }
  .footer-contact-item ul {
    list-style: none;
    padding: 0px;
  }
  .contact-item_title{
    font-size: 50px;
    font-weight: lighter;
    padding-top: 0.5em;
  }

  small a {
    font-weight: bold;
  }

  small {
    margin-top:30px;
    margin-bottom: 20px;
  }
  </style>
