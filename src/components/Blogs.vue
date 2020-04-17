<template>
  <div class="blogs col-6" @click="selectBlog()">
    <h3>{{blogsData.title}}</h3>
    user: {{blogsData.creatorEmail}}
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