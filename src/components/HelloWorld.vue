<template>
<div>
  <div>
    <ul>
       <li v-for="item in jokes" :key="item.id" class="joke-text">
        {{ item.joke }}
        </li>
    </ul>
  </div>
  <div v-if="msg.includes('can')">
    {{currentDate}}
  </div>
</div>
</template>

<script>
export default {
  name: 'HelloWorld',
  props: {
    msg: String,
    jokes: {
      type: Array,
      default: () => []
    }
  },
  data: function () {
    return {
      currentDate: new Date()
    }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
  .joke-text {
    text-align: left;
    color: blue;
    font-weight: 700;
  }
</style>
