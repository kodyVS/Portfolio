<template>
  <div class="about">
    <Button :text="backButton"></Button>
    <div class="introduction">
      <h2 class="title introduction__title">Introduction</h2>
      <p class="introduction__text">{{ introduction }}</p>
    </div>

    <div class="experience">
      <h2 class="title experience__title">
        Work Experience
      </h2>
      <div v-for="(experience, index) in experiences" :key="index" class="card">
        <p class="card__time">{{ experience.time }}</p>
        <div class="card__right">
          <h3 class="card__title">{{ experience.title }}</h3>
          <p class="card__description">{{ experience.description }}</p>
        </div>
      </div>
    </div>
  </div>
</template>
<script>
import Button from "@/components/Button.vue";
export default {
  components: {
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
      introduction: "Hello, my name is Kody Van Sloten and I am from Alberta, Canada.",
      experiences: [
        {
          time: " March 2022 - Present",
          title: "Nemic Hydroponics",
          description: "Developing full automation solutions for hydroponic farms",
        },
        {
          time: " September 2021 - March 2022",
          title: "Web Developer for Glean Asia",
          description:
            "During this time I lived abroad in Cambodia. I worked at Glean Asia building front-end components for Liferay-based software, designed databases and data structures for applications and built full-stack internal tools using vue.js and node",
        },
        {
          time: "December 2020 - September 2021",
          title: "Web Developer",
          description:
            "I started a company called NF Web Solutions. During this time I built full stack web apps working in Javascript frameworks.",
        },
        {
          time: "February 2020 - December 2020",
          title: "Learning Web Development",
          description:
            "During this period, I had the opportunity to dive into my passion for programming and learn languages and frameworks such as javascript, typescript, HTML, css, Vue, Angular, and Node. I created my first app, which is a trades management software",
        },
        {
          time: "March 2011 - February 2020",
          title: "Project Manager in Mechanical Trades",
          description:
            "I worked as a dual-ticketed mechanical contractor for Blackstone Mechanical, primarily focused on project management in commercial construction",
        },
      ],
    };
  },
};
</script>
<style lang="scss">
.about {
  margin: 0 auto;
  width: 80%;
  margin-top: 4rem;
}
.experience {
  padding-bottom: 10rem;
}
.title {
  font-size: 4.5rem;
  font-weight: 300;
  margin-bottom: 2rem;
  letter-spacing: 1px;
}
.introduction {
  margin-top: 2rem;
  &__text {
    font-size: 2.5rem;
    font-weight: 300;
    margin-bottom: 3rem;
    color: rgb(70, 70, 70);
  }
}
.card {
  background-color: rgba(255, 255, 255, 0.5);
  box-shadow: 0 3px 6px rgba(0, 0, 0, 0.16), 0 1.5px 3px rgba(0, 0, 0, 0.23);
  padding: 2rem;
  margin-top: 30px;
  margin-left: 1.5rem;
  font-size: 2.3rem;
  font-weight: 300;
  margin-bottom: 3rem;
  color: rgb(70, 70, 70);
  display: grid;
  grid-template-columns: minmax(300px, 400px) minmax(350px, 1fr);
  grid-gap: 2rem;
  transition: all 0.4s cubic-bezier(0.25, 0.8, 0.25, 1);
  &__title {
    color: rgb(27, 27, 27);
    margin-bottom: 1.2rem;
    font-weight: 300;
    font-size: 3.2rem;
  }
  &:hover {
    box-shadow: 0 14px 28px rgba(0, 0, 0, 0.25), 0 10px 10px rgba(0, 0, 0, 0.22);
  }
}
@media only screen and (max-width: 1300px) {
  .card {
    grid-template-columns: 1fr;
    margin: 5px 0 2rem 0;
    padding: 8px;
    font-size: 1.6rem;
    &__title {
      color: rgb(27, 27, 27);
      margin-bottom: 1.2rem;
      font-weight: 300;
      font-size: 2.5rem;
    }
  }
  .title {
    font-size: 3rem;
    font-weight: 300;
    letter-spacing: 0px;
  }
  .introduction {
    &__text {
      font-size: 2rem;
      font-weight: 300;
      margin-bottom: 3rem;
      color: rgb(70, 70, 70);
    }
  }
}
</style>
