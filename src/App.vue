<script setup>
  import ButtonCounter from './components/ButtonCounter.vue';
  import BlogPost from './components/BlogPost.vue'
</script>

<template>
  
  <div class="container">
    <h1>APP</h1>
    
    <ButtonCounter texto="Contador 1:"></ButtonCounter>
    <button-counter texto="Contador 2:"></button-counter>

    <BlogPost title="Post 1"></BlogPost>
    <BlogPost title="Post 2"></BlogPost>
    <BlogPost title="Post 3"></BlogPost>
  </div>
</template>