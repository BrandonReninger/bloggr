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
  methods: {},
  components: {}
};
</script>


<style scoped>
</style>