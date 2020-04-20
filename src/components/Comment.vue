<template>
  <div class="comment">
    <div class="row justify-content-center">
      <div class="col-6 d-flex">
        <p>{{commentData.body}}</p>
        <small>{{commentData.creatorEmail}}</small>
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
  methods: {},
  components: {}
};
</script>


<style scoped>
</style>