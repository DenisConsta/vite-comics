<script>
export default {
  name: "AppMain",
  props: {
    thumbs: Array,
  },
  data() {
    return {};
  },
};
</script>

<template>
  <main>
    <!-- ? JumboTron -->
    <div id="hero" class="">
      <img src="../assets/img/jumbotron.jpg" alt="" />
    </div>

    <!-- ? Main Content -->
    <div id="content" class="">
      <div class="container d-flex ">
        <!-- ? Row -->
        <div class="row row-cols-xl-4 row-cols-xxl-6">
          <!-- ? Col -->
          <div class="col mb-4" v-for="(thumb, index) in thumbs" :key="index">
            <!-- ? Thumb -->
            <div class="thumb ">
              <img :src="thumb.thumb" alt="" class="" />
              <h3>{{ thumb.series }}</h3>
            </div>
          </div>
        </div>

        <a class="my-btn">Load more</a>
      </div>
    </div>
  </main>
</template>

<style lang="scss" scoped>
@use "../styles/partials/variables" as *;
@use "../styles/partials/mixin" as *;

#hero {
  max-height: 400px;

  img {
    max-height: 400px;
    width: 100%;
    object-fit: cover;
    object-position: top;
  }
}

#content {
  background-color: $back-main;
  @include displayFlex("both");
  padding: 5rem 0;
  .container {
    @include displayFlex("both");
    flex-direction: column;
    position: relative;

    &::after {
      content: "Current series";
      display: block;
      color: white;
      text-transform: uppercase;
      font-family: "Roboto Condensed", sans-serif;
      position: absolute;
      background-color: $color-primary;
      font-size: 2rem;
      padding: 0 2rem;
      top: -18%;
      left: 0;
    }

    .my-btn {
      background-color: $color-primary;
      text-decoration: none;
      text-transform: uppercase;
      padding: 0.5rem 2rem;
      color: white;
      font-size: 0.8rem;
      font-family: "Roboto Condensed", sans-serif;
      letter-spacing: 1px;
      cursor: pointer;
    }
  }

  .thumb {
    flex-basis: 15%;
    @include displayFlex("both");
    flex-direction: column;
    cursor: pointer;

    img {
      height: 180px;
      aspect-ratio: 1/1;
      object-fit: cover;
      object-position: top;
    }

    h3 {
      color: white;
      font-size: 1rem;
      padding: 1rem 0;
      text-align: center;
      text-transform: uppercase;
      font-size: 0.85rem;
      font-family: "Open Sans", sans-serif;
    }
  }
}
</style>