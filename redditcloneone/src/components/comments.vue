<template >
  <div>
    <button type="button" v-on:click="show = !show" class="btn btn-default navbar-btn">See Comments</button>
    <div v-if='show'>
      <h5>Comments:</h5>
      <div class="panel panel-default">
        <div v-for="post in posts" class="panel-body text-left">

              <p><h5></h5>{{post.comments}}</p>

        </div>
      </div>
      <button type="button" v-on:click="logStuff" class="btn btn-default navbar-btn">Reply</button>
    </div>
  </div>
</template>

<script>
import posts from '../lib/post'
export default {
  props:['posts'],
  data () {
    return {
      user: "User101",
      show: false
    }
  },
  methods: {
    logStuff() {
      return console.log(this.posts[0].comments)
    }
  }
}
</script>

<style lang="css">
</style>
