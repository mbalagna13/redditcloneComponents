<template>
  <div>
    <form>
            <div class="row">
                <div class="col-xs-12 col-sm-8 col-sm-offset-2 col-md-6 col-md-offset-3">
                    <h4>Submit New Post</h4>
                    <hr>
                    <div class="form-group">
                        <label for="title">Title</label>
                        <input
                                type="text"
                                id="title"
                                v-model.lazy="post.title"
                                class="form-control">
                                <!-- :value="userData.email" -->
                                <!-- @input="userData.email = $event.target.value"> -->

                    </div>

                    <div class="form-group">
                        <label for="url">url</label>
                        <input
                                type="text"
                                id="url"
                                v-model.lazy="post.url"
                                class="form-control">

                    </div>
                </div>
            </div>
            <div class="row">
                <div class="col-xs-12 col-sm-8 col-sm-offset-2 col-md-6 col-md-offset-3 form-group">
                    <label for="description">Description</label><br>
                    <textarea
                            id="description"
                            rows="5"
                            class="form-control"
                            v-model.lazy="post.description">
                            </textarea>
                </div>
            </div>
            <div class="row">
                <div class="col-xs-12 col-sm-8 col-sm-offset-2 col-md-6 col-md-offset-3">
                    <button
                            class="btn btn-primary"
                            @click.prevent="addPost">Submit!
                    </button>
                </div>
            </div>
    </form>
    <hr>
    <p>{{post.title}}</p>
    <p>{{post.url}}</p>
    <p>{{post.description}}</p>
    <p>{{newMessage}}</p>
    <button type="button" name="button"
            @click="addPost()">Add new Post</button>
  </div>
</template>

<script>



export default {

  data () {
    return {
      message: "Navbar to forms, bruh",
      post :{
        title: '',
        description: '',
        url: '',
        counter:0
      }

    }
  },
  props: ['newMessage', 'onAddPost'],
  methods: {
    addPost() {
      this.onAddPost({
        title: this.post.title,
        description: this.post.description,
        url: this.post.url,
        counter:0
      });
      this.post.title = '';
      this.post.description = '';
      this.post.url = '';
    }
  }
}
</script>

<style lang="css">
</style>
