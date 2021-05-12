
<template>
   <div id="app">
      <router-view/>
      <main-tab-bar/>

  </div>
</template>

<script>
const MainTabBar=()=>import("components/content/mainTabBar/MainTabBar.vue")
export default {
  name: "App",
  components: {
    MainTabBar
  }
}
</script>


<style>
 @import 'assets/css/base.css';
</style>
