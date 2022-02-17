<template>
 <div class="test">
   <!-- <edit-change></edit-change> -->
  <nav-bar></nav-bar>
  <div class="right">
    <tab></tab>
  </div>
 </div>
</template>
<script>
import Tab from './components/Tab.vue'
import NavBar from './components/NavBar.vue'
  export default {
    components:{
      Tab,
      NavBar
    }
  };
</script>

<style scoped>
.test{
  display: flex;
}
.right {
  flex: 1;
}
</style>