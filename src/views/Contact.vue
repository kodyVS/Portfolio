<template>
  <div class="contact">
    <Button :text="backButton" class="contact__back-button"></Button>
    <div class="grid">
      <div class="left">
        <h3 class="contact__title">Contact me</h3>
        <p class="contact__description">
          Interested in working together? <br />
          Fill out the form with some info. <br />
          I will get back to you as soon as I can.
        </p>
        <div class="links">
          <div class="github" @click="goToRepo('https://github.com/kodyVS')">
            <Github class="contact__icon contact__icon--github"></Github>
          </div>
          <div
            class="linkedin"
            @click="goToRepo('https://www.linkedin.com/in/kody-van-sloten-b586b8176/')"
          >
            <Linkedin class="contact__icon contact__icon--github"></Linkedin>
          </div>
        </div>
      </div>
      <div class="right">
        <form action="https://formsubmit.co/kodyvansloten1@gmail.com" method="POST" class="form">
          <!-- Name -->
          <input
            class="form__input form__input--1"
            required
            name="name"
            v-model="contact.name"
            :placeholder="text.name"
            type="text"
            autocomplete="off"
          />
          <!-- Email -->
          <input
            class="form__input form__input--2"
            required
            name="email"
            v-model="contact.email"
            :placeholder="text.email"
            type="email"
            autocomplete="off"
          />
          <!-- Message -->
          <textarea
            class="form__input form__input--3"
            name="message"
            v-model="contact.message"
            rows="5"
            :placeholder="text.message"
          ></textarea>
          <input type="submit" value="Send Message" class="contact__button" />
        </form>
      </div>
    </div>
  </div>
</template>

<script>
import Button from "@/components/Button.vue";
import Github from "@/views/SVGIcons/Github.vue";
import Linkedin from "@/views/SVGIcons/Linkedin.vue";
export default {
  components: {
    Button,
    Github,
    Linkedin,
  },
  data() {
    return {
      text: {
        title: "Contact me",
        name: "Name",
        email: "E-mail",
        message: "Message",
      },
      contact: {
        name: "",
        email: "",
        message: "",
      },
      backButton: {
        icon: "ArrowLeft",
        text: "Go back",
        color: "#212529",
        to: "/",
      },
    };
  },
  methods: {
    goToRepo(link) {
      console.log("hello", window);
      window.open(link);
    },
  },
};
</script>

<style lang="scss">
.contact {
  margin-top: 4rem;
  position: relative;
  height: 100vh;
  width: 100vw;
  &__back-button {
    position: absolute;
    left: 10%;
  }
  &__title {
    font-size: 4rem;
    font-weight: 300;
    letter-spacing: 1px;
    margin-bottom: 3rem;
  }
  &__description {
    font-size: 2.5rem;
    color: rgb(88, 88, 88);
  }
  &__icon {
    padding: 1rem 1.8rem 1rem 0rem;
    height: 3rem;
    width: 3rem;
    opacity: 0.8;
    transition: all 0.2s;
    &:hover {
      opacity: 1;
      transform: scale(1.3);
      cursor: pointer;
    }
  }
  &__button {
    display: flex;
    font-family: Geomanist;
    font-weight: 600;
    padding: 0.5rem 1.3rem;
    align-items: center;
    justify-content: center;
    border: 3px solid transparent;
    height: 4rem;
    background-color: #f8f9fa;
    border-radius: 0.25rem;
    transition: all 0.2s ease-in;
    background-color: #6b0fc0;
    color: white;
    box-shadow: 0 3px 6px rgba(0, 0, 0, 0.16), 0 0px 3px rgba(0, 0, 0, 0.23);

    &:hover {
      background-color: #8012e7;
      cursor: pointer;
      transform: translateY(-2px);
      box-shadow: 0 7px 14px rgba(0, 0, 0, 0.25), 0 5px 5px rgba(0, 0, 0, 0.22);
    }
  }
  .links {
    display: flex;
  }
  .linkedin {
    fill: #0072b1;
  }
}
.grid {
  position: absolute;
  width: 100%;
  top: 50%;
  transform: translateY(-50%);

  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(400px, 1fr));
  justify-items: center;
}

.left {
  display: flex;
  flex-direction: column;
  width: 40rem;
}
.right {
  display: flex;
  flex-direction: column;
}
.form {
  width: 80%;
  &__input {
    box-sizing: border-box;
    width: 100%;
    padding: 1.2rem;
    margin-bottom: 3rem;
    border-radius: 8px;
    border: 1px solid rgb(189, 189, 189);
    font-family: "Geomanist";
    font-size: 1.6rem;
    background-color: rgb(254, 254, 254);
    resize: none;
  }
}
@media only screen and (max-width: 800px) {
  .grid {
    position: absolute;
    width: 100%;
    top: 50%;
    transform: translateY(-50%);

    display: grid;
    grid-template-columns: repeat(auto-fit, minmax(400px, 1fr));
    justify-items: start;
    margin-left: 3rem;
  }
}
</style>
