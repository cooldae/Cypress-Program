<template>
  <div class="home">
    <img alt="dot logo" src="../assets/dotLogo.png">
    <HelloWorld msg="Welcome"/>
  </div>
</template>

<script>
// @ is an alias to /src
import HelloWorld from '@/components/HelloWorld.vue'

export default {
  name: 'Home',
  components: {
    HelloWorld
  }
}
</script>
