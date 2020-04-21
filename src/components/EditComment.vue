<template>
  <div class="EditComment">
    <h3>Edit Comment</h3>
    <div class="d-flex flex-column justify-content-center col-6 bg-light mt-2 pb-2">
      <div class="form-group">
        <label for="comment"></label>
        <textarea
          type="text"
          class="form-control"
          placeholder="Enter Comment here"
          v-model="blog.comment"
        />
      </div>
      <button class="btn btn-sm btn-primary" type="button" @click="editComment()">SUBMIT</button>
    </div>
  </div>
</template>


<script>
export default {
  name: "EditComment",
  data() {
    return {};
  },
  computed: {
    blog() {
      return this.$store.state.activeBlog.blog;
    }
  },
  methods: {
    editComment() {
      this.$store.dispatch("editComment", this.blog.comment);
    }
  },
  components: {}
};
</script>


<style scoped>
</style>