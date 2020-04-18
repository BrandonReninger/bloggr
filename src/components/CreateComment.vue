<template>
  <div class="create-comment col-6">
    <div class="form-group">
      <label for="body"></label>
      <textarea
        type="text"
        name="body"
        class="form-control"
        placeholder="Comment here"
        {{commentData.comment}}
        v-model="newComment.comment"
      />
    </div>
    <small>{{commentData.creatorEmail}}</small>
  </div>
</template>


<script>
export default {
  name: "create-comments",
  data() {
    return {};
  },
  computed: {},
  methods: {
    addComment() {}
  },
  components: {}
};
</script>


<style scoped>
</style>