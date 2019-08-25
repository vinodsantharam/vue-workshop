<template>
  <div class="home">
    <img alt="Vue logo" src="../assets/logo.png">
    <HelloWorld v-bind:msg="homeMessage"/>
  </div>
</template>

<script>
// @ is an alias to /src
import HelloWorld from '@/components/HelloWorld.vue'
import axios from 'axios'

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

    axios.get('http://api.icndb.com/jokes/random/5')
      .then(result => {
        console.log(result.data.value)
        this.homeMessage = result.data.value[0].joke
      })
  }
}
</script>
