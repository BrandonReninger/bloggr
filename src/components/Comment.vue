<template>
  <div class="comment">
    <div class="row mt-3 justify-content-center">
      <div class="col-6 bg-info text-light mb-2 d-flex flex-column">
        <p>{{commentData.body}}</p>
        <small>{{commentData.creatorEmail}}</small>
        <button
          @click="deleteComment()"
          v-show="this.commentData.creatorEmail == $auth.userInfo.email"
          type="button"
          class="close text-"
        >
          <span>&times;</span>
        </button>
        <button
          @click="editCom=!editCom"
          v-show="this.commentData.creatorEmail == $auth.userInfo.email"
          class="btn btn-primary"
        >EDIT</button>
        <EditComment v-if="editCom"></EditComment>
      </div>
    </div>
  </div>
</template>


<script>
import EditComment from "./EditComment";
export default {
  name: "comment",
  props: ["commentData"],
  data() {
    return {
      editCom: false
    };
  },
  computed: {
    comments() {
      return this.$store.state.comments;
    },
    blog() {
      return this.$store.state.activeBlog.comments;
    }
  },
  methods: {
    async deleteComment(id) {
      await this.$store.dispatch("deleteComment", id);
      this.$store.dispatch("selectBlog", this.commentData.blogId);
    }
  },
  components: { EditComment }
};
</script>


<style scoped>
</style>