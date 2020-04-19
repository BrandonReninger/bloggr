<template>
  <div class="create-comment col-6 d-flex flex-column">
    <div class="form-group">
      <label for="body"></label>
      <textarea
        type="text"
        name="body"
        class="form-control"
        placeholder="Comment here"
        v-model="newComment.body"
      />
    </div>
    <button class="btn btn-sm btn-primary" @click="addComment()">Comment</button>
  </div>
</template>


<script>
export default {
  name: "create-comment",
  data() {
    return {
      newComment: {}
    };
  },
  computed: {},
  methods: {
    //ANCHOR start here tomorrow, addComment and getComments need to be tied to blogId!!
    addComment() {
      this.$store.dispatch("addComment", this.newComment);
      this.newComment = {};
    },

    getComments() {
      this.$store.dispatch("getComments", { id: blog.id });
    }
  },
  components: {}
};
</script>


<style scoped>
</style>