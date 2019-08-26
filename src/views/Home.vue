<template>
  <div class="home">
    <img alt="Vue logo" src="../assets/logo.png">
    <button v-on:click='updateJokes'>update jokes</button>
    <HelloWorld v-bind:msg="homeMessage" v-bind:jokes="chucksJokes" v-on:liked="onJokeLiked"/>
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
      homeMessage: 'Welcome to Your Vue.js App bla-bla-bla',
      chucksJokes: []
    }
  },
  mounted: function () {
    this.homeMessage = 'Home is updated after mounted'
  },
  methods: {
    updateJokes: function () {
      axios.get('http://api.icndb.com/jokes/random/5')
        .then(result => {
          console.log(result.data.value)
          this.homeMessage = result.data.value[0].joke
          this.chucksJokes = result.data.value
        })
    },
    onJokeLiked: function (event) {
      alert(event)
    }
  }
}
</script>
