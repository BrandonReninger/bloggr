<template>
  <div class="home">
    <h1 class="text-center">Was geht auf?</h1>
    <CreateBlog v-if="$auth.isAuthenticated"></CreateBlog>
    <div class="row d-flex justify-content-center">
      <h3>Things n' Stuff to Read</h3>
    </div>
    <div class="row d-flex">
      <Blogs v-for="blog in blogs" :blogsData="blog" :key="blog._id"></Blogs>
    </div>
  </div>
</template>

<script>
import Blogs from "../components/Blogs";
import CreateBlog from "../components/CreateBlog";
export default {
  name: "home",
  data() {
    return {};
  },
  mounted() {
    this.$store.dispatch("getBlogs");
  },
  computed: {
    blogs() {
      return this.$store.state.blogs;
    },
    created() {
      this.$store.dispatch("getBlogs");
    }
  },
  components: { CreateBlog, Blogs }
};
</script>

<style scoped>
</style>
