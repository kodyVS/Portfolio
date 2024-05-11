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
          image: "CrewConnect.png",
          title: "Crew Connect - 2024",
          description: "Marketplace for skilled trades",
          tags: ["Nuxt", "Node", "Vue", "Capacitor"],
          link: "https://crew-connect.ca",
          github: false,
        },
        {
          image: "Nemic.png",
          title: "Nemic Hydroponics - 2023",
          description: "Automation system for hydroponics farms",
          tags: ["python", "Nuxt", "Vue", "SQL"],
          link: "https://nemic-hydroponics.com/",
          github: false,
        },
        {
          image: "FNConvert.png",
          title: "FN Convert - 2023",
          description:
            "App that utilizes AI to convert field notes into professional notes ready for invoicing, summarizing, and exporting client facing documents.",
          tags: ["Nuxt", "OpenAI", "Nodejs", "Docker"],
          link: "https://noteconverter.com/",
          github: false,
        },
        {
          image: "Boilerplate.png",
          title: "Web App Boilerplate - 2022",
          description:
            "Production ready Nuxt 3 and Node.js + Typescript boilerplate for starting apps.",
          tags: ["Nuxt", "Node.js", "Typescript", "MongoDb"],
          link: "https://github.com/kodyVS/Nuxt-Vuetify-Express-Typescript-Boilerplate",
          github: true,
        },
        {
          image: "TradesTek2.png",
          title: "TradesTek - 2021",
          description:
            "Web App for managing mechanical trades for scheduling, invoicing, jobsite management and finances",
          tags: ["Vue", "Vuetify", "Nodejs", "MongoDb"],
          link: "https://github.com/kodyVS/TradesTek",
          github: true,
        },
        {
          image: "OfficeWatch.png",
          title: "Office Watch - 2021",
          description: "A place for remote workers to find offices based off of their careers",
          tags: ["Vue", "Javascript", "SCSS", "Typescript", "NestJS"],
          link: "https://github.com/Nergy101/NWS.OfficeWatch",
          github: true,
        },
        {
          image: "daikumoto.png",
          title: "Dai Ku Moto - 2020",
          description: "Website built for Dai Ku Moto's landing page",
          tags: ["Vue", "Javascript", "SCSS"],
          link: "https://daikumoto.netlify.app/",
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
  padding: 4rem;
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
    padding: 4rem 0 0 0;

    &__back-button {
      margin-bottom: 4rem;
      margin-left: 4rem;
    }
  }
}
</style>
