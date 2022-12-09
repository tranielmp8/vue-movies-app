<template>
  <div class="movie-detail" >
    <h2>{{movie.Title}}</h2>
    <p>{{movie.Year}}</p>
    <img :src="movie.Poster" alt="Movie Poster" class="featured-img">
    <p>{{movie.Plot}}</p>
  </div>
</template>

<script setup>
import { ref, onBeforeMount } from 'vue'
import { useRoute } from 'vue-router'
import env from '@/env.js'

  const movie = ref({})
  const route = useRoute()

  onBeforeMount(() => {
    fetch(`http://www.omdbapi.com/?apikey=${env.apikey}&i=${route.params.id}&plot=full`)
    .then(response => response.json())
    .then(data => {
      movie.value = data;
    })
  })

</script>

<style lang="scss" scoped>
  .movie-detail {
    padding: 16px;
    max-width: 600px;
    margin: 15px auto;

    h2{ 
      color: #fff;
      font-size: 28px;
      font-weight: 600;
      margin-bottom: 16px;
      text-align: center;
    }

    .featured-img {
      display: block;
      max-width: 500px;
      margin-bottom: 16px;
      margin: 15px auto;
      border-radius: 8px;
      
    }

    p {
      color: #fff;
      font-size: 18px;
      line-height: 1.4;
      text-align: center;
    }

  }

  @media screen and (max-width: 600px){
    .movie-detail {
      max-width: 350px;
    }

    .featured-img {
      max-width: 400px;
    }
  }
</style>