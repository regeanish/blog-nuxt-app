<template>
    <!-- static component -->
     <!-- <nuxt-link to="'/posts/' + 1" class="post-preview">
        <article>
          <div class="post-thumbnail" style="background-image:url('https://images.unsplash.com/photo-1515879218367-8466d910aaa4?ixlib=rb-1.2.1&ixid=eyJhcHBfaWQiOjEyMDd9&auto=format&fit=crop&w=1350&q=80')"></div>
          <div class="post-content">
            <h1>Post Title</h1>
            <p>Preview Text</p>
          </div>
        </article>
      </nuxt-link> -->

     <nuxt-link :to="'/posts/' + id" class="post-preview">
        <article>
          <div class="post-thumbnail" :style="{backgroundImage: 'url(' + thumbnail + ')'}"></div>
          <div class="post-content">
            <h1>{{title}}</h1>
            <p>{{previewText}}</p>
          </div>
        </article>
      </nuxt-link>
</template>

<script>
export default {
    name:'PostPreview',
    props: {
        id: {
            type:String,
            required:true
        },
        title: {
            type:String,
            required:true
        },
        previewText:{
            type:String,
            required:true
        },
        thumbnail:{
            type:String,
            required:true
        }
    }
}
</script>

<style scoped>
.post-preview {
  border: 1px solid #ccc;
  box-shadow: 0 2px 2px #ccc;
  background-color: white;
  width: 90%;
}

a {
  text-decoration: none;
  color: black;
}

@media (min-width: 850px) {
  .post-preview {
    width: 400px;
    margin: 10px;
  }
}

.post-thumbnail {
  width: 100%;
  height: 200px;
  background-position: center;
  background-size: cover;
}

.post-content {
  padding: 10px;
  text-align: center;
}

a:hover .post-content,
a:active .post-content {
  background-color: #ccc;
}
</style>