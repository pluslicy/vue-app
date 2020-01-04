<template>
  <div class="home">
    <header class="header">
      <img src="../../assets/home.jpg" alt="">
    </header>
   
  </div>
</template>
<script>
import {mapState, mapActions} from 'vuex'
export default {
  
  created(){
  },
  methods:{

  }
}
</script>
<style scoped>
.home {
  padding-bottom: 50px;
}
.header {
  height: 300px;
  overflow: hidden;
}
.header img {
  width: 100%;
}
</style>