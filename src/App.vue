<template>
  <div>
    <app-header></app-header>
    <router-view></router-view>
  </div>
</template>

<script>
import AddBlog from './components/AddBlog.vue'
import ShowBlogs from './components/ShowBlogs.vue'
import Header from './components/Header.vue'

export default {
  components:  {
    'add-blog': AddBlog,
    'show-blogs': ShowBlogs,
    'app-header': Header,
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
body {
  margin: 0;
  font-family: 'Nunito', sans-serif;
}
</style>
