<template>
  <button @click="$router.push(text.to)" class="button">
    <div class="button__icon">
      <component
        :is="text.icon"
        :iconStyle="'height:2rem;color:' + text.color"
      ></component>
    </div>
    <p class="button__text">{{ text.text }}</p>
  </button>
</template>
<script>
import ArrowLeft from "@/views/SVGIcons/ArrowLeft.vue";
import HTML from "@/views/SVGIcons/HTML.vue";
import LightBulb from "@/views/SVGIcons/LightBulb.vue";
import Message from "@/views/SVGIcons/Message.vue";
import Person from "@/views/SVGIcons/Person.vue";
import Star from "@/views/SVGIcons/Star.vue";
export default {
  props: ["text"],
  components: {
    ArrowLeft,
    HTML,
    LightBulb,
    Message,
    Person,
    Star,
  },
};
</script>
<style lang="scss">
.button {
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
  transition: color 0.15s ease-in-out, background-color 0.15s ease-in-out,
    border-color 0.15s ease-in-out, box-shadow 0.15s ease-in-out;

  &__icon {
    margin-right: 10px;
    margin-top: 3px;
  }
  &__text {
    font-size: 1.9rem;
  }
  &:hover {
    color: #212529;
    background-color: #e2e6ea;
    border-color: #dae0e5;
    cursor: pointer;
  }
}
</style>
