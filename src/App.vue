<template>
  <countries></countries>
  <randomAnime></randomAnime>
  <animeRecomendacion></animeRecomendacion>
</template>

<script>
import countries from './components/infoCountries.vue'
import animeRecomendacion from './components/animeRecomendacion.vue';
import randomAnime from './components/randomAnimeManga.vue';

export default {
  name: 'App',
  components: {
    countries,
    randomAnime,
    animeRecomendacion
  }
}
</script>

<style>
</style>
