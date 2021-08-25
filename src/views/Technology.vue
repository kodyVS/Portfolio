<template>
  <div class="technology">
    <Button :text="backButton"></Button>
    <div class="frontend">
      <h2 class="title">
        Frontend
      </h2>
      <div class="frontend__cards">
        <TechCard
          v-for="(card, index) in frontend"
          :key="index"
          :cardData="card"
          class="frontend__card"
        >
        </TechCard>
      </div>
    </div>
    <div class="backend">
      <h2 class="title">
        Back End
      </h2>
      <div class="frontend__cards">
        <TechCard
          v-for="(card, index) in backend"
          :key="index"
          :cardData="card"
          class="frontend__card"
        >
        </TechCard>
      </div>
    </div>
    <div class="others">
      <h2 class="title">
        Others
      </h2>
      <div class="frontend__cards">
        <TechCard
          v-for="(card, index) in others"
          :key="index"
          :cardData="card"
          class="frontend__card"
        >
        </TechCard>
      </div>
    </div>
  </div>
</template>
<script>
import TechCard from "@/components/TechCard.vue";
import Button from "@/components/Button.vue";
export default {
  components: {
    TechCard,
    Button,
  },
  data() {
    return {
      backButton: {
        icon: "ArrowLeft",
        text: "Go back",
        color: "#212529",
        to: "/",
      },
      frontend: [
        {
          title: "Vue",
          logo: "Vue.png",
          link: "https://vuejs.org/",
        },
        {
          title: "Angular",
          logo: "Angular.png",
          link: "https://angular.io/",
        },
        {
          title: "Typescript",
          logo: "Typescript.png",
          link: "https://www.typescriptlang.org/index.html",
        },
        {
          title: "Javascript",
          logo: "Javascript.png",
          link: "https://en.wikipedia.org/wiki/JavaScript",
        },
        {
          title: "HTML5",
          logo: "HTML5.png",
          link: "https://en.wikipedia.org/wiki/HTML5",
        },
        {
          title: "CSS3",
          logo: "CSS3.png",
          link: "https://en.wikipedia.org/wiki/Cascading_Style_Sheets#CSS_3",
        },
        {
          title: "Bootstrap",
          logo: "Bootstrap.png",
          link: "https://getbootstrap.com/",
        },
      ],

      backend: [
        {
          title: "NodeJs",
          logo: "NodeJs.png",
          link: "https://nodejs.org/en/",
        },

        {
          title: "Firebase",
          logo: "Firebase.png",
          link: "https://firebase.google.com/",
        },
        {
          title: "MongoDB",
          logo: "MongoDb.png",
          link: "https://www.mongodb.com/",
        },
      ],

      others: [
        {
          title: "Electron",
          logo: "Electron.png",
          link: "https://www.electronjs.org/",
        },
        {
          title: "Git",
          logo: "Git.png",
          link: "https://git-scm.com/",
        },
        {
          title: "Photoshop",
          logo: "Photoshop.png",
          link: "https://www.adobe.com/ca/products/photoshop.html",
        },
        {
          title: "Illustrator",
          logo: "Illustrator.png",
          link: "https://www.adobe.com/ca/products/illustrator.html",
        },
      ],
    };
  },
};
</script>
<style lang="scss">
.title {
  font-size: 4rem;
  font-weight: 300;
  margin: 4rem 0 2rem 0;
}
.technology {
  margin: 0 auto;
  margin-top: 5rem;
  width: 90%;
}
.frontend {
  background-color: transparent;
  &__cards {
    display: grid;
    grid-template-columns: repeat(auto-fill, 16rem);
    grid-gap: 4rem;
    background-color: transparent;
    justify-content: center;
  }
}
@media only screen and (max-width: 400px) {
  .frontend {
    background-color: transparent;
    &__cards {
      display: grid;
      grid-template-columns: repeat(auto-fit, 15rem);
      grid-gap: 1rem;
      background-color: transparent;
      justify-content: center;
    }
  }
}
</style>
