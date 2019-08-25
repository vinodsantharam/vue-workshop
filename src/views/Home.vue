<template>
  <div class="home">
    <img alt="Vue logo" src="../assets/logo.png">
    <HelloWorld v-bind:msg="homeMessage"/>
  </div>
</template>

<script>
// @ is an alias to /src
import HelloWorld from '@/components/HelloWorld.vue'

export default {
  name: 'home',
  components: {
    HelloWorld
  },
  data: function () {
    return {
      homeMessage: 'Welcome to Your Vue.js App bla-bla-bla'
    }
  },
  mounted: function () {
    this.homeMessage = 'Home is updated after mounted'
  }
}
</script>
