<template>
  <div>
    <nav class="navbar navbar-default navbar-fixed-top">
      <div class="container">
    <!-- Brand and toggle get grouped for better mobile display -->
        <div class="navbar-header">
          <a class="navbar-brand" href="#">Michael's Reddit Clone</a>
        </div>
        <div class="nav navbar-nav navbar-right">
          <button type="button" v-on:click="show = !show" class="btn btn-default navbar-btn">Submit New Post</button>
          <button class="btn btn-default" @click='AlertWithAlert' type="submit">See What Happens</button>
        </div>
      </div><!-- /.container-fluid -->
    </nav>


    <!-- form component -->
    <newpostform :newMessage='newMessage'
                  @messageChanged='newMessage = $event'
                  v-if="show"
                  :onAddPost="onAddPost"></newpostform>
    <p>{{newMessage}}</p>
  </div>
</template>

<script>
import submitForm from './forms.vue'

export default {
  props: ['onAddPost'],
  data () {
    return {
      newMessage: '',
      message: "Hello From nav.vue",
      show: false
    }
  },
  components: {
    'newpostform': submitForm
  },
  methods: {
    AlertWithAlert () {
      console.log('Nothing!');
    }
  }

}
</script>

<style lang="css">
</style>
