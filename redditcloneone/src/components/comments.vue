<template >
  <div>
    <button type="button" v-on:click="show = !show" class="btn btn-default navbar-btn">See Comments</button>
    <div v-if='show'>
      <h5>Comments:</h5>
      <div class="panel panel-default">
        <div class="panel-body text-left">
          <p><h5>{{user}}:</h5>{{comment}}</p>
        </div>
      </div>
      <button type="button" v-on:click="show = !show" class="btn btn-default navbar-btn">Reply</button>
    </div>
  </div>
</template>

<script>
export default {
  data () {
    return {
      comment: "Hello!",
      user: "User101",
      show: false
    }
  }
}
</script>

<style lang="css">
</style>
