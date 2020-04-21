<template>
  <div class="blog-detail">
    <div class="row justify-content-center">
      <div class="col-6 d-flex flex-column bg-light mt-2 pb-2">
        <div class="row justify-content-center">
          <div class="col-4 d-flex">
            <img class="img-fluid img-thumbnail mt-2" :src="blog.imgUrl" />
          </div>
        </div>
        <h3>{{blog.title}}</h3>
        <p>{{blog.body}}</p>
        <small>{{blog.creatorEmail}}</small>
        <button class="edit btn btn sm btn-success" @click="edit=!edit">EDIT</button>
        <button class="btn btn-sm btn-primary" @click="$router.push({name: 'Home'})">BACK</button>
        <button class="btn btn-sm btn-danger" type="button" @click="deleteBlog()">DELETE</button>
      </div>
    </div>
    <EditBlog v-if="edit"></EditBlog>
    <!--<EditComment v-if="editCom"></EditComment>-->

    <div class="row justify-content-center">
      <CreateComment class="col-6"></CreateComment>
    </div>
    <Comment v-for="comment in comments" :commentData="comment" :key="comment._id"></Comment>
  </div>
</template>


<script>
import CreateComment from "../components/CreateComment";
import Comment from "../components/Comment";
import EditBlog from "../components/EditBlog";
//import EditComment from "../components/EditComment";
export default {
  name: "blog-details",
  //props: ["blogData"],
  data() {
    return {
      edit: false
      //editCom: false
    };
  },
  created() {
    this.$store.dispatch("selectBlog", this.$route.params.blogId);
  },
  computed: {
    blog() {
      return this.$store.state.activeBlog.blog;
    },
    comments() {
      return this.$store.state.activeBlog.comments;
    }
  },
  methods: {
    deleteBlog() {
      this.$router.push({ name: "Home" });
      this.$store.dispatch("deleteBlog", this.blog._id);
    }
  },
  components: {
    CreateComment,
    Comment,
    EditBlog
    //EditComment
  }
};
</script>


<style scoped>
.edit {
  background-color: green;
}

button {
  margin-top: 0.5rem;
}
</style>