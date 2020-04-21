<template>
  <div v-show="this.$auth.userInfo.email == blog.creatorEmail" class="editBlog">
    <h3>Edit Blog</h3>
    <div class="d-flex flex-column justify-content-center col-6 bg-light mt-2 pb-2">
      <div class="form-group">
        <label for="title"></label>
        <input type="text" class="form-control" placeholder="Title here" v-model="blog.title" />
      </div>
      <div class="form-group">
        <label for="body"></label>
        <textarea
          type="text"
          class="form-control"
          placeholder="Enter blog here"
          v-model="blog.body"
        />
      </div>
      <div class="form-group">
        <label for="imgUrl"></label>
        <input type="url" class="form-control" placeholder="image url here" v-model="blog.imgUrl" />
      </div>
      <button class="btn btn-sm btn-primary" type="button" @click="editBlog()">SUBMIT</button>
    </div>
  </div>
</template>


<script>
export default {
  name: "editBlog",
  data() {
    return {};
  },
  computed: {
    blog() {
      return this.$store.state.activeBlog.blog;
    }
  },
  methods: {
    editBlog() {
      this.$store.dispatch("editBlog", this.blog);
    }
  },
  components: {}
};
</script>


<style scoped>
</style>