<script setup>
  import {ref, computed, onMounted} from "vue";

  import BlogPost from './components/BlogPost.vue';
  import PaginatePost from './components/PaginatePost.vue';
  import LoadingSpinner from './components/LoadingSpinner.vue';

  const posts = ref([]);
  const favorito = ref('');

  const postXpage = 10;
  const inicio = ref(0);
  const final = ref(postXpage);

  const loading = ref(true);

  const cambiarFavorito = (titulo) => {
    favorito.value = titulo;
  }

  const prev = () => {
    inicio.value -= postXpage;
    final.value -= postXpage;
  }

  const next = () => {
    inicio.value += postXpage;
    final.value += postXpage;
  }

  onMounted(async() =>{

    try {
      
      const res = await fetch('https://jsonplaceholder.typicode.com/posts');
      posts.value = await res.json();

    } catch (error) {
      console.log(error);
    }finally{
      
      setTimeout(() =>{
        loading.value = false

      }, 2000);

    }

  })

  // fetch('https://jsonplaceholder.typicode.com/posts')
  //   .then(res => res.json())
  //   .then(data => posts.value = data)
  //   .catch(e => console.log(e))
  //   .finally(() => {
  //     setTimeout(() => {
        
  //       loading.value = false
  //     }, 2000)
  //   });

  const maxLength = computed(() => posts.value.length);
</script>

<template>
  
  <LoadingSpinner v-if="loading"></LoadingSpinner>

  <div class="container" v-else>
    <h1>APP</h1>
    <h2>Mi Post Favorito: {{favorito}}</h2>

    <PaginatePost
      class="mb-2"
      @prev = "prev"
      @next = "next"
      :inicio="inicio"
      :final="final"
      :maxLength = "maxLength"
    ></PaginatePost>

    <BlogPost
      v-for="post in posts.slice(inicio, final)"
      :key="post.id"
      :title="post.title"
      :id="post.id" 
      :body="post.body"
      :cambiarFavorito="cambiarFavorito"
      class="mb-2">
    </BlogPost>
  </div>
</template>