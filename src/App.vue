<template lang="pug">
  .container
    router-view
</template>

<script>

export default {
  name: 'app',
  components: {
  },
  data () {
    return {
      
    }
  }
}
</script>

<style lang="scss">
  body {
    font-family: "Helvetica neue", Helvetica, sans-serif;
    font-size: 16px;
    line-height: 1.42;
    -webkit-font-smoothing: antialiased;
    background: #f5f5f5;
  }

  .container {
    width: 600px;
    margin: 0 auto;
  }

  ul {
    margin: 0;
    padding: 0;
  }

  li {
    list-style: none;
  }

  * {
    box-sizing: border-box;
  }
</style>
