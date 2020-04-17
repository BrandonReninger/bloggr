<template>
  <div class="blog-details">
    <img class="img-fluid" :src="blogData.imgUrl" />
    <h3>{{blogData.title}}</h3>
    <p>{{blogData.body}}</p>
    <small>{{blogData.creatorEmail}}</small>
    <button class="btn btn-sm btn-danger" type="button" @click="deleteBlog()">DELETE</button>
  </div>
</template>


<script>
export default {
  name: "blog-details",
  props: ["blogData"],
  data() {
    return {};
  },
  computed: {
    blog() {
      return this.$store.state.activeBlog;
    }
  },
  methods: {},
  components: {}
};
</script>


<style scoped>
</style>