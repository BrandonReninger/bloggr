<template>
  <div class="blogs col-6 d-flex flex-column" @click="selectBlog()">
    <h3>{{blogsData.title}}</h3>
    <small>author: {{blogsData.creatorEmail}}</small>
  </div>
</template>


<script>
export default {
  name: "blogs",
  props: ["blogsData"],
  data() {
    return {};
  },
  computed: {},
  methods: {
    selectBlog() {
      this.$store.commit("setActiveBlog", {});
      this.router.push({
        name: "BlogDetails",
        params: { blogId: this.blogData._id }
      });
    }
  },
  components: {}
};
</script>


<style scoped>
</style>