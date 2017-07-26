<template>
  <div>
    <p>{{newMessage}}</p>

        <h4>Search Posts</h4>
        <input v-model='filterText'>
          <ul>
            <li v-for='posts in filterPosts'>
                  <hr>
              <div class="container">
                <div class="row">
                  <div class="col-xs-12 col-sm-8 ">
                    <div class="media-left">
                          <!-- <img v-bind:src="posts.url" class="rounded float-left" style="width:200px;height:200px"> -->
                          <img class="media-object" v-bind:src="posts.url" style="width:200px;height:200px">
                    </div>
                    <div class="media-body">
                      <h4 class="media-heading">
                        <a href="#"><span class="glyphicon glyphicon-arrow-up" @click="posts.counter++"></span></a>
                        <span>{{posts.counter}}</span>
                        <a href="#"><span class="glyphicon glyphicon-arrow-down" @click="posts.counter--"></span></a>
                        {{posts.title}}</h4>

                        {{posts.description}}

                      </div>
                  </div>
                </div>
              </div>
                      <hr>
                      <comments></comments>
            </li>
          </ul>
    </div>

  </div>
</template>

<script>
import comments from './comments.vue'

export default {
  methods: {
    created() {
      eventBus.$on('messageChanged', (data) => {
        this.newMessage = data
      })
    }
  },
  components: {
    'comments': comments
  },
  data() {
    return {
      show: false,
      newMessage: "Welcome to Michael's poorly designed reddit clone. He's trying. Really.",
      filterText: '',
      submits: [
        {title: 'Calvin And Hobbes',
         description: "Best comic books series ever made! Now that we know who you are, I know who I am. I'm not a mistake! It all makes sense! In a comic, you know how you can tell who the arch-villain's going to be? He's the exact opposite of the hero. And most times they're friends, like you and me! I should've known way back when... You know why, David? Because of the kids. They called me Mr Glass.",
         url: 'http://www.calvinandhobbes.com/wp-content/uploads/sites/7/2016/09/about_main_image1.png',
         counter: 2,
         comments: ''

        },

        {title: 'Holy Smokes',
        description:"Your bones don't break, mine do. That's clear. Your cells react to bacteria and viruses differently than mine. You don't get sick, I do. That's also clear. But for some reason, you and I react the exact same way to water. We swallow it too fast, we choke. We get some in our lungs, we drown. However unreal it may seem, we are connected, you and I. We're on the same curve, just on opposite ends.",
        url: 'https://i.ytimg.com/vi/SlqXrnvxlA8/maxresdefault.jpg',
        counter: 45,
        comments: ''
        },

        {title: 'Gumball',
        description: "I like this catoon.Well, the way they make shows is, they make one show. That show's called a pilot. Then they show that show to the people who make shows, and on the strength of that one show they decide if they're going to make more shows. Some pilots get picked and become television programs. Some don't, become nothing. She starred in one of the ones that became nothing.",
        url: 'https://i.ytimg.com/vi/4DJ8X_yU9q0/maxresdefault.jpg',
        counter: 5,
        comments: ''

        },

        {title: 'The Greatest Game of Rock, Paper, Scissors',
        description: "First episode of Regular Show. Also the best episode. Look, just because I don't be givin' no man a foot massage don't make it right for Marsellus to throw Antwone into a glass motherfuckin' house, fuckin' up the way the nigger talks. Motherfucker do that shit to me, he better paralyze my ass, 'cause I'll kill the motherfucker, know what I'm sayin'?",
        url: 'http://ibdp.huluim.com/video/60519231?size=720x405',
        counter: 200,
        comments: ''

        }
    ]
  }
}, computed: {
  filterPosts (){
    return this.submits.filter((element) => {
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
