<template>
  <div class="create-blog">
    <div class="form-group">
      <label for="title"></label>
      <input type="text" class="form-control" placeholder="Title here" v-model="newBlog.title" />
    </div>
    <div class="form-group">
      <label for="body"></label>
      <input type="text" class="form-control" placeholder="Enter blog here" v-model="newBlog.body" />
    </div>
    <div class="form-group">
      <label for="imgUrl"></label>
      <input type="url" class="form-control" placeholder="Title here" v-model="newBlog.imgUrl" />
    </div>
    <div class="form-group">
      <label for="published"></label>
      <input type="text" class="form-control" placeholder="Your name" v-model="newBlog.published" />
    </div>
    <div class="form-group">
      <label for="creatorEmail"></label>
      <input
        type="text"
        class="form-control"
        placeholder="Title here"
        v-model="newBlog.creatorEmail"
      />
    </div>
  </div>
</template>


<script>
export default {
  name: "create-blog",
  data() {
    return {
      newJoke: {}
    };
  },
  computed: {},
  methods: {},
  components: {}
};
</script>


<style scoped>
</style>