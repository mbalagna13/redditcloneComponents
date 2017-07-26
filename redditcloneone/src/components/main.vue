<template>
  <div>
    <navbar></navbar>
    <postcomp></postcomp>
  </div>
</template>

<script>
import navBar from './nav.vue'
import postcomp from './postcomp.vue'

export default {
  name: 'app',
  components: {
    'navbar': navBar,
    'postcomp': postcomp
  },
  data () {
    return {
    }
  }
}
</script>




<style>
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}

h1, h2 {
  font-weight: normal;
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
