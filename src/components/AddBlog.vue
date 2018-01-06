<template>
  <div id="add-blog">
    <h2>Add a new blog post</h2>
    <form>
      <label>Blog Title :</label>
      <input type="text" v-model.lazy="blog.title" />
      <label>Blog Content :</label>
      <textarea v-model.lazy="blog.content" cols="30" rows="10"></textarea>
      <div id="checkboxes">
        <label>Front-end</label>
        <input type="checkbox" value="Front-end" v-model="blog.categories" />
        <label>Back-end</label>
        <input type="checkbox" value="Back-end" v-model="blog.categories" />
        <label>Design</label>
        <input type="checkbox" value="Design" v-model="blog.categories" />
        <label>Integration</label>
        <input type="checkbox" value="Integration" v-model="blog.categories" />
      </div>

      <div id="preview">
        <h3>Preview Blog</h3>
        <p>Blog title : {{blog.title}}</p>
        <p>Blog content : </p>
        <p>{{blog.content}}</p>
        <p>Blog Categories : </p>
        <ul v-for="category in blog.categories">
          <li>{{ category }}</li>
        </ul>
      </div>
    </form>

  </div>
</template>

<script>
export default {
  data () {
    return {
      blog:  {
        title: "",
        content: "",
        categories: []
      }
    }
  },
  methods:  {

  }
}
</script>

<style>

#add-blog * {
  box-sizing: border-box;
}
#add-blog {
  margin: 20px auto;
  max-width: 500px;
}
label {
  display: block;
  margin: 20px 0 10px;
}
input[type="text"], textarea {
  display: block;
  width: 100%;
  padding: 8px;
} 
#preview {
  padding: 10px 20px;
  border: 1px dotted #ccc;
  margin: 30px 0;
}
h3 {
  margin-top: 10px;
}

#checkboxes input{
  display: inline-block;
  margin-right: 10px;
}

#checkboxes label {
  display: inline-block;
}
</style>
