<script>
export default {
  name: 'AppFooter',
  props:{
      links: Object
  },

  data(){
    return{

    }
  },
  methods: {
    getPathImage(imageName) {
      return new URL(`../assets/img/${imageName}`, import.meta.url).href;
    },
  }
}
</script>

<template>
  <footer>
    <!-- ? Top Footer -->
    <div id="top-footer" class="">
      <div class="container  h-100">
        <div class="row h-100">

          <!-- ? links -->
          <div class="col links-col d-flex justify-content-between">
            <nav v-for="(nav, index) in links.navs " :key="index" class="py-5 px-2">
              <h3>{{nav.listName}}</h3>
              <ul>
                <li v-for="(link, i) in nav.items" :key="i">
                  <a href="#">{{link}}</a>
                </li>
              </ul>
            </nav>
          </div>

          <!-- ? Logo -->
          <div class="col logo-bg d-none d-lg-block"></div>
        </div>
      </div>
    </div>
    
    <!-- ? Bottom Footer -->
    <div id="bottom-footer" class="">
      <div class="container ">
        <div class="my-btn">Sign-up now!</div>
        <nav class="d-flex ">
          <h3 class="d-none d-md-block">Follow us</h3>
          <ul class="d-flex m-0 gap-3">
            <li v-for="(icon, i) in links.socials" :key="i">
              <img :src="getPathImage(icon)" :alt="icon">
            </li>
          </ul>
        </nav>
      </div>
    </div>
  
  </footer>
</template>

<style lang="scss" scoped>
@use '../styles/partials/variables' as *;
@use '../styles/partials/mixin' as *;

#top-footer{
  background-image: url('../assets/img/footer-bg.jpg');
  background-size: cover;

  .logo-bg{
    background-image: url('../assets/img/dc-logo-bg.png');
    background-size: cover;
    background-position: center;
  }

  .links-col{
    
    h3{
      text-transform: uppercase;
      font-family: "Roboto Condensed", sans-serif;
      color: white;
    }

    a{
      color: rgb(156, 154, 154);
      text-transform: capitalize;

      &:hover{
        color: white;
      }
    }

    ul{
      padding: 0;
      margin: 0;
    }
  }
}

#bottom-footer{
  @include displayFlex('both');
  height: 120px;
  background-color: $back-footerBottom;
  font-family: "Roboto Condensed", sans-serif;
  .my-btn{
    color: white;
    border: 2px solid $color-primary;
    text-transform: uppercase;
    padding: .5rem 1rem;
    cursor: pointer;
  }

  .container{
    @include displayFlex('between');
    
    h3{
      color: $color-primary;
      text-transform: uppercase;
      margin: 0;
    }

    ul li img{
      cursor: pointer;
    }
  }

  
}


</style>