<template>
  <div class="home">
   <img alt="barberLogo" src="../assets/Bb.jpg">
    <HelloWorld msg="Bienvenidos BARBER -SHOP-"/>
    
  </div>
</template>

<script>
// @ is an alias to /src
import HelloWorld from '@/components/HelloWorld.vue'

export default {
  name: 'HomeView',
  components: {
    HelloWorld
  }
}
</script>
