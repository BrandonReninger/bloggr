<template>
  <div class="home">
    <CreateBlog v-if="$auth.isAuthenticated"></CreateBlog>
    <blogs></blogs>
    <h1>Welcome</h1>
  </div>
</template>

<script>
import Blogs from "../components/Blogs";
import CreateBlog from "../components/Blogs";
export default {
  name: "home",
  data() {
    return {};
  },
  mounted() {
    //this.$store.dispatch("getBlogs");
  },
  components: { CreateBlog }
};
</script>
