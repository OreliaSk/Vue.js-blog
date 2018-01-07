<template>
  <div>
    <router-view></router-view>
  </div>
</template>

<script>
import AddBlog from './components/AddBlog.vue'
import ShowBlogs from './components/ShowBlogs.vue'

export default {
  components:  {
    'add-blog': AddBlog,
    'show-blogs': ShowBlogs,
  },
  data () {
    return {
    }
  },
  methods:  {

  }
}
</script>

<style>
  * {
    margin: 0;
    font-family: 'Nunito', sans-serif;
  }
</style>
