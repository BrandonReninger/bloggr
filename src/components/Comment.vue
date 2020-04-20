<template>
  <div class="comment">
    <div class="row mt-3 justify-content-center">
      <div class="col-6 bg-info text-light mb-2 d-flex flex-column">
        <p>{{commentData.body}}</p>
        <small>{{commentData.creatorEmail}}</small>
        <button @click="deleteComment()" type="button" class="close text-">
          <span>&times;</span>
        </button>
      </div>
    </div>
  </div>
</template>


<script>
export default {
  name: "comment",
  props: ["commentData"],
  data() {
    return {};
  },
  computed: {
    comments() {
      return this.$store.state.comments;
    }
  },
  methods: {
    deleteComment() {
      this.$store.dispatch("deleteComment", this.commentData);
    }
  },
  components: {}
};
</script>


<style scoped>
</style>