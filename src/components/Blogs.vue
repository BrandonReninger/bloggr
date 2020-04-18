<template>
  <div class="blogs col-6 d-flex flex-column">
    <h3>{{blogsData.title}}</h3>
    <small>author: {{blogsData.creatorEmail}}</small>
    <button v-if="$auth.isAuthenticated" @click="selectBlog()">View Blog</button>
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
      this.$router.push({
        name: "BlogDetails",
        params: { blogId: this.blogsData._id }
      });
    }
  },
  components: {}
};
</script>


<style scoped>
</style>