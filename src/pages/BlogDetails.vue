<template>
  <div class="blog-details col-6">
    <img class="img-fluid" :src="blog.imgUrl" />
    <h3>{{blog.title}}</h3>
    <p>{{blog.body}}</p>
    <small>{{blog.creatorEmail}}</small>
    <button class="btn btn-sm btn-primary" @click="$router.push({name: 'Home'})">BACK</button>
    <button class="btn btn-sm btn-danger" type="button" @click="deleteBlog()">DELETE</button>
    <CreateComment></CreateComment>
  </div>
</template>


<script>
import CreateComment from "../components/CreateComment";
export default {
  name: "blog-details",
  //props: ["blogData"],
  data() {
    return {};
  },
  created() {
    this.$store.dispatch("selectBlog", this.$route.params.blogId);
  },
  computed: {
    blog() {
      return this.$store.state.activeBlog;
    }
  },
  methods: {},
  components: {
    CreateComment
  }
};
</script>


<style scoped>
</style>