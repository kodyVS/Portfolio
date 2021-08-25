<template>
  <div class="home">
    <div class="content">
      <h1 class="content__title">
        Hello, <span class="content__title__span--3">my name is</span> <br />
        <span class="content__title__span--1"
          >&nbsp;
          <vue-typer
            :repeat="0"
            pre-type-delay="1000"
            type-delay="100"
            @typed="onTyped"
            text="Kody Van Sloten"
          ></vue-typer
        ></span>
        <br />
        <span class="content__title__span--2"
          >&nbsp;<vue-typer
            v-if="typed"
            :repeat="0"
            pre-type-delay="1000"
            type-delay="50"
            @typed="onTyped"
            text="and I am a web developer."
          ></vue-typer
        ></span>
        <br />
      </h1>
      <div class="content__buttons">
        <Button class="content__button" :text="aboutMeButton"></Button>
        <Button class="content__button" :text="knowButton"></Button>
        <Button class="content__button" :text="projectsButton"></Button>
        <Button class="content__button" :text="contactButton"></Button>
      </div>
    </div>
  </div>
</template>

<script>
// @ is an alias to /src
import Button from "@/components/Button.vue";
import { VueTyper } from "vue-typer";
export default {
  name: "Home",
  components: {
    Button,
    VueTyper,
  },
  data() {
    return {
      typed: false,
      aboutMeButton: {
        text: "About me",
        icon: "Person",
        color: "#343a40",
        to: "/about",
      },
      knowButton: {
        text: "Things I know",
        icon: "LightBulb",
        color: "#ffc107",
        to: "/technology",
      },
      projectsButton: {
        text: "My Projects",
        icon: "HTML",
        color: "#28a745",
        to: "/projects",
      },
      contactButton: {
        text: "Contact me",
        icon: "Message",
        color: "#6b0fc0",
        to: "/contact",
      },
    };
  },
  methods: {
    onTyped() {
      this.typed = true;
    },
  },
};
</script>
<style lang="scss">
.home {
  position: relative;
  height: 100vh;
}
.content {
  position: absolute;
  top: 35vh;
  left: 20vh;
  display: flex;
  flex-direction: column;

  &__title {
    font-weight: 300;
    margin-bottom: 10px;
    &__span--1 {
      font-size: 6rem;
      font-weight: 300;
      letter-spacing: 2px;
      margin-top: 1rem;
    }
    &__span--2 {
      font-size: 3.5rem;
      display: block;
      font-weight: 300;
      text-align: center;
      margin-top: 1rem;
    }
    &__span--3 {
      color: #6b0fc0;
    }
  }
  &__buttons {
    display: flex;
    flex-wrap: wrap;
    width: 40rem;
  }
  &__button {
    margin-right: 1.5rem;
    margin-top: 1.5rem;
  }
}
@media only screen and (max-width: 800px) {
  .content {
    top: 50%;
    left: 50%;
    transform: translate(-50%, -50%);
    align-items: center;
    &__buttons {
      justify-content: center;
    }
    &__title {
      font-weight: 300;
      margin-bottom: 10px;
      width: fit-content;
      &__span--1 {
        display: inline;
        font-size: 4.5rem;
        font-weight: 300;
        letter-spacing: 2px;
        margin-top: 1rem;
      }
      &__span--2 {
        font-size: 2.5rem;
        display: inline;
        font-weight: 300;
        text-align: center;
      }
    }
  }
}
</style>
