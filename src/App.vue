<script>
import AppFooterVue from './components/AppFooter.vue';

import AppHeader from './components/AppHeader.vue';
import AppMain from './components/AppMain.vue';
import AppShop from './components/AppShop.vue';
import AppFooter from './components/AppFooter.vue';

import links from './data/menu'
import shop from './data/shop';
import dcComics from './data/dc-comics'

export default {
  name: 'App',
  components:{
    AppHeader,
    AppMain,
    AppShop,
    AppFooter
  },
  data(){
    return{
      links,
      shop,
      dcComics
    }
  }
}
</script>

<template>
    <AppHeader :menu="links" />
    <AppMain :thumbs="dcComics"/>
    <AppShop :shop="shop" />
    <AppFooter/>
</template>

<style lang="scss">
@use './styles/general.scss'


</style>