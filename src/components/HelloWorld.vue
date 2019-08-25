<template>
<div>
  <div>
    {{msg}}
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
    msg: String
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

</style>
