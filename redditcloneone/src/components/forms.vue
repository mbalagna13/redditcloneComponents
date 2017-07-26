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
                                v-model.lazy="title"
                                class="form-control">
                                <!-- :value="userData.email" -->
                                <!-- @input="userData.email = $event.target.value"> -->

                    </div>

                    <div class="form-group">
                        <label for="url">url</label>
                        <input
                                type="text"
                                id="url"
                                v-model.lazy="url"
                                class="form-control">

                    </div>
                </div>
            </div>
            <div class="row">
                <div class="col-xs-12 col-sm-8 col-sm-offset-2 col-md-6 col-md-offset-3 form-group">
                    <label for="description">Description</label><br>
                    <textarea
                            id="eescription"
                            rows="5"
                            class="form-control"
                            v-model.lazy="description">
                            </textarea>
                </div>
            </div>
            <div class="row">
                <div class="col-xs-12 col-sm-8 col-sm-offset-2 col-md-6 col-md-offset-3">
                    <button
                            class="btn btn-primary"
                            @click.prevent="submitted">Submit!
                    </button>
                </div>
            </div>
    </form>
    <hr>
    <p>{{title}}</p>
    <p>{{url}}</p>
    <p>{{description}}</p>
    <p>{{newMessage}}</p>
    <button type="button" name="button"
            @click="editMessage()">Change that message</button>
  </div>
</template>

<script>

import eventBus from '../main.js'

export default {
  data () {
    return {
      message: "Navbar to forms, bruh",
      title: '',
      description: '',
      url: ''
    }
  },
  props: ['newMessage'],
  methods: {
    editMessage() {
      this.newMessage = 'did this work?';
      // this.$emit('messageChanged', this.newMessage)
      eventBus.$emit('messageChanged', this.newMessage)
    }
  }
}
</script>

<style lang="css">
</style>
