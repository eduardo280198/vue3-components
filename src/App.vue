<script setup>
  import {ref} from "vue";

  import ButtonCounter from './components/ButtonCounter.vue';
  import BlogPost from './components/BlogPost.vue'

  const posts = ref([
    {title: "Post 1", id: 1, body: "Descripción 1"},
    {title: "Post 2", id: 2, body: "Descripción 2"},
    {title: "Post 3", id: 3, body: "Descripción 3"},
    {title: "Post 4", id: 4},
    {title: "Post 5", id: 5, body: "Descripción 5"},
  ]);
</script>

<template>
  
  <div class="container">
    <h1>APP</h1>
    
    <ButtonCounter texto="Counter 1:"></ButtonCounter>
    <button-counter texto="Counter 2:"></button-counter>

    <BlogPost
      v-for="post in posts"
      :key="post.id"
      :title="post.title"
      :id="post.id" 
      :body="post.body">
    </BlogPost>
  </div>
</template>