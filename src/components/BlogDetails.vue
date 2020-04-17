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