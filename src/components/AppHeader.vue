<script>
export default {
  name: 'AppHeader',
  props:{
    menu: Array,
  },
  data(){
    return{
    }
  }
}
</script>

<template>
  <header>
    <div class="container ">
      <nav class="d-flex justify-content-between align-items-center ">
        <!-- ? Logo -->
        <div class="logo">
          <img src="../assets/img/dc-logo.png" alt="DC-Logo">
        </div>

        <!-- ? Links -->
        <div class="links  ">
          <ul class="d-flex gap-4  m-0">
            <li v-for="(link, index) in menu" :key="index" ><a :href="link.href" :class="{'active' : link.current}">{{link.text}}</a></li>
          </ul>
        </div>

      </nav>
    </div>
  </header>
</template>

<style lang="scss" scoped>
@use '../styles/partials/variables' as *;
@use '../styles/partials/mixin' as *;

nav{
  padding: 1rem 0;

  .logo img{
    max-height: 80px;
  }

  .links li a{
    color: rgb(94, 90, 90);
    text-transform: uppercase;
    font-family: "Roboto Condensed", sans-serif;
    font-weight: 600;
    font-size: .9rem;

    &:hover,
    &.active{
      color: $color-primary;

      &::after{
        content: '';
        position: relative;
        bottom: -140%;
        display: block;
        height: 5px;
        width: 100%;
        background: $color-primary;
      }
    }
  }
}

</style>