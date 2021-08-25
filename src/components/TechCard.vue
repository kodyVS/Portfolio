<template>
  <div class="tech-card">
    <v-lazy-image
      :src="require(`../assets/img/logos/logo-medium/${cardData.logo}`)"
      :src-placeholder="
        require(`../assets/img/logos/logo-small/${cardData.logo}`)
      "
      alt="Tech Image"
      class="tech-card__image"
    />
    <p class="tech-card__title">{{ cardData.title }}</p>
  </div>
</template>
<script>
import VLazyImage from "v-lazy-image";
export default {
  props: ["cardData"],
  components: {
    VLazyImage,
  },
};
</script>
<style lang="scss">
.tech-card {
  display: flex;
  flex-direction: column;
  height: 16rem;
  width: 16rem;
  background-color: white;
  text-align: center;
  align-items: center;
  justify-content: center;
  border-radius: 3px;
  padding: 0.5rem;
  border: 2px solid rgba(234, 234, 234, 0.44);
  box-shadow: 0 3px 6px rgba(0, 0, 0, 0.16), 0 1.5px 3px rgba(0, 0, 0, 0.23);
  transition: all 0.2s ease-in;
  &__image {
    height: 9rem;
    width: 9rem;
    margin-bottom: 1.7rem;
  }
  &__title {
    font-size: 2.4rem;
  }
  &:hover {
    transform: translateY(-3px);
    box-shadow: 0 14px 28px rgba(0, 0, 0, 0.25), 0 10px 10px rgba(0, 0, 0, 0.22);
    cursor: pointer;
  }
}
@media only screen and (max-width: 400px) {
  .tech-card {
    height: 12rem;
    width: 12rem;
    &__image {
      height: 6rem;
      width: 6rem;
      margin-bottom: 1.7rem;
    }
  }
}
</style>
