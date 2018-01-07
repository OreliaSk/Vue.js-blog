<template>
  <div id="show-blogs">
    <h1>All Blog Articles</h1>
    <input type="text"v-model="search" placeholder="Search blogs" />
    <div v-for="blog in filteredBlogs" class="single-blog">
      <router-link v-bind:to="'/blog/' + blog.id"><h2 v-rainbow>{{ blog.title }}</h2></router-link>
      <article>{{ blog.content | snippet }}</article>
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
    this.$http.get('https://vuejs-blog-711ae.firebaseio.com/posts.json').then(function(data){
        return data.json();
    }).then(function(data){
      let blogsArray = [];
      for(let key in data){
        data[key].id = key;
        blogsArray.push(data[key]);
      }
      this.blogs = blogsArray;
    });
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
#show-blogs{
    max-width: 800px;
    margin: 0px auto;
}
h1 {
  text-align: center;
}
.single-blog{
    padding: 20px;
    margin: 20px 0;
    box-sizing: border-box;
    background: #eee;
    border: 1px dotted #aaa;
}
#show-blogs a{
    color: #444;
    text-decoration: none;
}
input{
    padding: 10px;
    width: 100%;
    box-sizing: border-box;
}
</style>
