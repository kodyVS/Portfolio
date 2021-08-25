<template>
  <div class="project-card" @click="goToRepo(project.link)">
    <v-lazy-image
      class="project-card__image"
      :src="require(`../assets/img/projects-medium/${project.image}`)"
      :src-placeholder="
        require(`../assets/img/projects-small/${project.image}`)
      "
      alt="project image"
    />
    <div class="project-card__text">
      <h3 class="project-card__title">{{ project.title }}</h3>
      <p class="project-card__description">{{ project.description }}</p>
    </div>

    <div class="project-card__tags">
      <div
        class="project-card__tag"
        v-for="(tag, index) in project.tags"
        :key="index"
      >
        {{ tag }}
      </div>
    </div>

    <Button
      @click="goToRepo(project.link)"
      v-if="project.github"
      class="project-card__button"
      :text="repoButton"
    ></Button>
    <Button
      @click="goToRepo(project.link)"
      v-else
      class="project-card__button"
      :text="websiteButton"
    ></Button>
  </div>
</template>
<script>
import Button from "@/components/Button.vue";
import VLazyImage from "v-lazy-image";
export default {
  props: ["project"],
  components: {
    Button,
    VLazyImage,
  },
  data() {
    return {
      repoButton: {
        icon: "Star",
        text: "Visit Repository",
      },
      websiteButton: {
        icon: "Star",
        text: "Visit website",
      },
    };
  },
  methods: {
    goToRepo(link) {
      if (link) {
        window.open(link);
      }
    },
  },
};
</script>
<style lang="scss">
.project-card {
  display: flex;
  flex-direction: column;
  align-items: flex-start;
  background-color: white;
  justify-content: space-between;
  width: 100%;
  min-height: 63rem;
  margin-bottom: 5rem;
  border-radius: 3px;
  overflow: hidden;
  box-shadow: 0 0px 0px rgba(0, 0, 0, 0.16), 0 0px 3px rgba(0, 0, 0, 0.23);
  transition: all 0.2s ease-in;
  & > *:not(:first-child) {
    margin-left: 2rem;
  }
  &__image {
    width: 100%;
    margin-bottom: 3rem;
  }
  &__text {
    margin-right: 1rem;
  }
  &__title {
    font-size: 2.8rem;
    font-weight: 600;
    margin-bottom: 0.5rem;
    padding-right: 0.5rem;
  }
  &__description {
    font-size: 2.2rem;
    margin-bottom: 3rem;
  }
  &__tag {
    background-color: #343a40;
    color: white;
    display: inline-block;
    padding: 5px 1.5rem;
    border-radius: 100px;
    font-weight: 600;
    margin-right: 1.2rem;
    margin-bottom: 1rem;
  }
  &__button {
    margin-bottom: 2rem;
  }
  &:hover {
    transform: translateY(-1.5rem);
    box-shadow: 0 14px 28px rgba(0, 0, 0, 0.25), 0 10px 10px rgba(0, 0, 0, 0.22);
    cursor: pointer;
  }
}
@media only screen and (max-width: 800px) {
  .project-card {
  }
}
</style>
