<template>
  <div class="blog-details row justify-content-center">
    <div class="col-6 d-flex flex-column bg-light mt-2 pb-2">
      <div class="row justify-content-center">
        <div class="col-4 d-flex">
          <img class="img-fluid img-thumbnail mt-2" :src="blog.imgUrl" />
        </div>
      </div>
      <h3>{{blog.title}}</h3>
      <p>{{blog.body}}</p>
      <small>{{blog.creatorEmail}}</small>
      <button class="btn btn-sm btn-primary" @click="$router.push({name: 'Home'})">BACK</button>
      <button class="btn btn-sm btn-danger" type="button" @click="deleteBlog()">DELETE</button>
    </div>
    <div class="row">
      <CreateComment></CreateComment>
    </div>
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
      return this.$store.state.activeBlog.blog;
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