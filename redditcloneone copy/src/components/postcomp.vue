<template>
  <div>
    <p>{{newMessage}}</p>

        <h4>Search Posts</h4>
        <input v-model='filterText'>
          <ul>
            <li v-for='post in filterPosts'>
                  <hr>
              <div class="container">
                <div class="row">
                  <div class="col-xs-12 col-sm-8 ">
                    <div class="media-left">
                          <!-- <img v-bind:src="posts.url" class="rounded float-left" style="width:200px;height:200px"> -->
                          <img class="media-object" v-bind:src="post.url" style="width:200px;height:200px">
                    </div>
                    <div class="media-body">
                      <h4 class="media-heading">
                        <a ><span class="glyphicon glyphicon-arrow-up" @click="post.counter++"></span></a>
                        <span>{{post.counter}}</span>
                        <a><span class="glyphicon glyphicon-arrow-down" @click="post.counter--"></span></a>
                        {{post.title}}</h4>

                        {{post.description}}

                      </div>
                  </div>
                </div>
              </div>
                      <hr>
                      <comments
                        :posts='posts'></comments>
            </li>
          </ul>
    </div>

  </div>
</template>

<script>
import comments from './comments.vue'

export default {
  props: ['posts'],

  components: {
    'comments': comments
  },
  data() {
    return {
      show: false,
      newMessage: "Welcome to Michael's poorly designed reddit clone. He's trying. Really.",
      filterText: '',
  }
}, computed: {
  filterPosts (){
    return this.posts.filter((element) => {
      // console.log(element.title);
      return element.title.toLowerCase().match(this.filterText.toLowerCase())
    })
  }
}
}

</script>

<style>
</style>




<!-- possible styling options -->



<!-- <div class="col-xs-12 col-sm-8 col-sm-offset-2 col-md-6 col-md-offset-3">
  <img v-bind:src="posts.url" class="rounded float-left" style="width:200px;height:200px">
  <h3>{{posts.title}} </h3>
  <span class="glyphicon glyphicon-arrow-up" @click="posts.counter++"></span>
  <span>{{posts.counter}}</span>
  <span class="glyphicon glyphicon-arrow-down" @click="posts.counter--"></span>
  <p>{{posts.description}}</p>

  <hr>
</div> -->

<!-- <div v-for="posts in submits">
    <h3>{{posts.title}} </h3>
    <span class="glyphicon glyphicon-arrow-up" @click="posts.counter++"></span>
    <span>{{posts.counter}}</span>
    <span class="glyphicon glyphicon-arrow-down" @click="posts.counter--"></span>
    <p>{{posts.description}}</p>
    <img v-bind:src="posts.url" class="rounded float-left" style="width:200px;height:200px">
    <hr>
  </div> -->
  <!-- <div class="col-xs-12 col-sm-8 col-sm-offset-2 col-md-6 col-md-offset-3">
    <h3>{{value}}</h3>
    <p>{{value}}</p>
    <img v-bind:src="value" class="rounded float-left" style="width:200px;height:200px">
  </div> -->
