<template>
  <div>
    <nav-bar class="nav">
      <div slot="center">cy购物街</div>
    </nav-bar>
    <home-swiper :banners="banners"/>
  </div>
</template>

<script>
import NavBar from 'components/common/navbar/NavBar.vue'
import {getHomeMultidata,getProductData} from 'network/home'
import HomeSwiper from './childComponents/HomeSwiper'


export default {
  components: { 
    NavBar,
    HomeSwiper },
  name: 'Home',
  data() {
    return {
      banners: [],
      recommends: [],
    }
    
  },
  created() {
   getHomeMultidata().then(res => {
     this.banners=res.data.banner.list;
     this.recommends=res.data.recommend.list;
    //  console.log(this.banners[0]);
   })
  }
}
</script>

<style>
  .nav{
    text-align: center;
    color: white;
    background-color: var(--color-tint);
  }
</style>