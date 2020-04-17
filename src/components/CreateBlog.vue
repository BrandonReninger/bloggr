<template>
  <div class="create-blog d-flex flex-column justify-content-center col-6 bg-light mt-2 pb-2">
    <div class="form-group">
      <label for="title"></label>
      <input type="text" class="form-control" placeholder="Title here" v-model="newBlog.title" />
    </div>
    <div class="form-group">
      <label for="body"></label>
      <textarea
        type="text"
        class="form-control"
        placeholder="Enter blog here"
        v-model="newBlog.body"
      />
    </div>
    <div class="form-group">
      <label for="imgUrl"></label>
      <input type="url" class="form-control" placeholder="image url here" v-model="newBlog.imgUrl" />
    </div>
    <!--<div class="form-group">
      <label for="published"></label>
      <input type="text" class="form-control" placeholder="Your name" v-model="newBlog.published" />
    </div>-->
    <!--<div class="form-group">
      <label for="creatorEmail"></label>
      <input
        type="text"
        class="form-control"
        placeholder="Your email"
        v-model="newBlog.creatorEmail"
      />
    </div>-->
    <button class="btn-lg btn-primary" type="button" @click="addBlog()">SUBMIT</button>
  </div>
</template>


<script>
export default {
  name: "create-blog",
  data() {
    return {
      newBlog: {}
    };
  },
  computed: {},
  methods: {
    addBlog() {
      this.$store.dispatch("addBlog", this.newBlog);
      this.newBlog = {};
    }
  },
  components: {}
};
</script>


<style scoped>
</style>