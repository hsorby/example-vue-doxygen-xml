<template>
  <div class="hello">
    <h1>{{ msg }}</h1>
    <p>
      Navigating to the <router-link to="/help">help page</router-link> will
      show the rendered output of the source Doxygen XML content.
    </p>
  </div>
</template>

<script>
export default {
  name: 'HomeContent',
  props: {
    msg: String
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped lang="scss">
h3 {
  margin: 40px 0 0;
}
ul {
  list-style-type: none;
  padding: 0;
}
li {
  display: inline-block;
  margin: 0 10px;
}
a {
  color: #42b983;
}
</style>
