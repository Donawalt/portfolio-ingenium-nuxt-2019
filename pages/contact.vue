<template>
  <div class="container content">
    <section class="tag">
      <p class="we">
        <span ref="a">CONTACT</span>
      </p>
      <div class="form-container">
        <form name="contact" action="https://app.99inbound.com/api/e/6dzYzcoN" method="post">
        <label class="form-label" for="name">
          Name:
        </label>
        <input class="form-field" name="name" id="name" />
        <label class="form-label" for="email">
          Email:
        </label>
        <input class="form-field" name="email" id="email" />
        <label class="form-label" for="message">
          Message:
        </label>
        <textarea class="form-field" name="message" id="message"></textarea>
        <input class="form-button" type="submit" value="Send message" />
      </form>
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

  form{
    display: flex;
    flex-direction: column;
    width: 100%;
    max-width: 600px;
    margin-top: 10px;
  }

  .form-container{
    display: flex;
    justify-content: center;
    align-items: center;
    width: 100%;
  }
  .form-field{
    min-height: 50px;
    margin-bottom: 10px;
    border-radius: 10px;
    border: 1.5px solid white;
    padding-left: 20px;
    background-color: black;
    font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
    color: grey;
    transition: 500ms;
  }

  .form-field:focus{
    background-color: white;
    transition: 500ms;
    color: black;
  }

  .form-field[name=message]{
    padding-top: 20px;
    padding-right: 20px;
  }
  input[type=submit]{
    height: 50px;
    background-color: darkslategrey;
    color: white;
    border: none;
    align-self: center;
    width:50%;
    max-width: 200px;
    border-radius: 25px;
    text-transform: uppercase;
    font-weight: bold; 
  }
</style>
