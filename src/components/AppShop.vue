<script>
export default {
  name: "AppShop",
  props: {
    shop: Array,
  },
  data() {
    return {};
  },
  methods: {
    getPathImage(imageName) {
      return new URL(`../assets/img/${imageName}`, import.meta.url).href;
    },
  },
};
</script>

<template>
  <section id="shop">
    <div class="container h-100">
      <ul
        class="
          d-flex
          justify-content-between
          align-items-center
          m-0
          px-4
          w-100
          gap-5
        "
      >
        <li v-for="(link, index) in shop" :key="index" class="">
          <img :src="getPathImage(link.img)" alt="link.text" />
          <a>{{ link.text }}</a>
        </li>
      </ul>
    </div>
  </section>
</template>

<style lang="scss" scoped>
@use "../styles/partials/variables" as *;
@use "../styles/partials/mixin" as *;

#shop {
  height: 140px;
  background-color: $color-primary;

  .container {
    @include displayFlex("both");
  }

  ul li {
    @include displayFlex("both");
    gap: 1rem;
    cursor: pointer;

    a {
      text-decoration: none;
      text-transform: uppercase;
      color: white;
      font-size: 0.85rem;
      font-weight: 400;
      font-family: "Open Sans", sans-serif;
    }

    img {
      height: 50px;
      max-width: 50px;
    }
  }
}
</style>