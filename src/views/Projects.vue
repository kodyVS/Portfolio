<template>
  <div class="projects">
    <Button class="projects__back-button" :text="backButton"></Button>
    <h2 class="projects__title">Projects</h2>
    <div class="projects__cards">
      <ProjectCard
        v-for="(project, index) in projects"
        :key="index"
        :project="project"
        class="projects__card"
      ></ProjectCard>
    </div>
  </div>
</template>
<script>
import ProjectCard from "@/components/ProjectCard.vue";
import Button from "@/components/Button.vue";
export default {
  components: {
    ProjectCard,
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
      projects: [
        {
          image: "TradesTek2.png",
          title: "TradesTek",
          description:
            "Web App for managing mechanical trades for scheduling, invoicing, jobsite management and finances",
          tags: ["Vue", "Vuetify", "Nodejs", "Mongodb"],
          link: "",
          github: false,
        },
        {
          image: "daikumoto.png",
          title: "Dai Ku Moto",
          description: "Website built for Dai Ku Moto's landing page",
          tags: ["Vue", "Javascript", "SCSS"],
          link: "https://clever-tereshkova-772ddd.netlify.app/",
          github: false,
        },
        {
          image: "DiscordBot.png",
          title: "Programming Server Bot",
          description:
            "A magnificent bot built by a group for my programming discord server.",
          tags: ["Python"],
          link: "https://github.com/kodyVS/Discord-Bot-Development",
          github: true,
        },
        {
          image: "CFR-2.png",
          title: "Cambodia Food Reviews",
          description:
            "Headless CMS blog built with Nuxt and Ghost. Used for blogging food adventures in Cambodia.",
          tags: ["Vue", "Ghost", "Nuxt", "Figma"],
          link: "https://www.cambodiafoodreview.com",
          github: false,
        },
        // {
        //   image: "",
        //   title: "MEVN and Nuxt Boilerplate with Auth",
        //   description:
        //     "Headless CMS blog built with Nuxt and Ghost. Used for blogging food adventures in Cambodia",
        //   tags: ["Vue", "Ghost", "Nuxt", "Figma"],
        //   link: "https://www.cambodiafoodreview.com",
        //   github: false,
        // },
      ],
    };
  },
};
</script>
<style lang="scss">
.projects {
  margin: 4rem;
  &__back-button {
    margin-bottom: 4rem;
    margin-left: 10rem;
  }
  &__title {
    margin-bottom: 5rem;
    font-size: 3rem;
    margin-left: 10rem;
  }
  &__cards {
    display: grid;
    grid-template-columns: repeat(auto-fit, 40rem);
    justify-content: center;
    gap: 5rem;
  }
  &__card {
    margin-right: 2rem;
  }
}
@media only screen and (max-width: 800px) {
  .projects {
    &__cards {
      grid-template-columns: 0.8fr;
    }
    &__card {
      margin-right: 0rem;
    }
    margin: 4rem 0 0 0;
  }
}
</style>
