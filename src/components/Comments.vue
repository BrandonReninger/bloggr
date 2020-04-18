<template>
  <div class="comments col-6">
    <div class="form-group">
      <label for="body"></label>
      <textarea
        type="text"
        name="body"
        class="form-control"
        placeholder="Comment here"
        {{commentData.comment}}
      />
    </div>
    <small>{{commentData.creatorEmail}}</small>
  </div>
</template>


<script>
export default {
  name: "comments",
  data() {
    return {};
  },
  computed: {},
  methods: {},
  components: {}
};
</script>


<style scoped>
</style>