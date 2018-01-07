<template>
  <div id="show-blogs">
    <h1 id="blog-articles-title">All Blog Articles</h1>
    <input type="text"v-model="search" placeholder="search blogs" />
    <div v-for="blog in filteredBlogs" class="single-blog">
      <router-link v-bind:to="'/blog/' + blog.id"><h2 v-rainbow>{{ blog.title }}</h2></router-link>
      <article>{{ blog.body | snippet }}</article>
    </div>
  </div>
</template>

<script>

export default{
  data() {
    return {
      blogs: [],
      search: ''
    }
  },
  methods:{

  },
  created(){
    this.$http.get('https://jsonplaceholder.typicode.com/posts').then(function(data){
      this.blogs = data.body.slice(0, 10);

    })
  },
  computed:{
    filteredBlogs() {
      return this.blogs.filter((blog) => {
        return blog.title.match(this.search);
      });
    }
  },
  filters:{
    snippet(value){
      return value.slice(0, 100) +  ' ...';
    },

  },
  directives:{
    'rainbow':{
      bind(el, binding, vnode){
      el.style.color = "#"+ Math.random().toString().slice(2, 8);
  }
    }
  }

}
</script>

<style>
#show-blogs {
  max-width: 800px;
  margin: 0 auto;
}
.single-blog {
  padding: 20px;
  margin: 20px 0;
  box-sizing: border-box;
  background: #eee;
}
#blog-articles-title {
  text-align: center;
}
input {
  width: 100%;
}
</style>
