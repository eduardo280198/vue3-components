<script setup>
  import ButtonCounter from './components/ButtonCounter.vue';
  import BlogPost from './components/BlogPost.vue'
</script>

<template>
  
  <div class="container">
    <h1>APP</h1>
    
    <ButtonCounter texto="Counter 1:"></ButtonCounter>
    <button-counter texto="Counter 2:"></button-counter>

    <BlogPost
      title="Post 1"
      :id="1" 
      body="Descripción 1">
    </BlogPost>
    
    <BlogPost
      title="Post 2"
      :id="2"
      body="Descripción 2">
    </BlogPost>

    <BlogPost
      title="Post 3"
      :id="3"
      body="Descripción 3">
    </BlogPost>

    <BlogPost
      title="Post 4"
      :id="4">
    </BlogPost>
  </div>
</template>