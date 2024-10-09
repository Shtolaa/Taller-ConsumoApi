<template>
    <h2>Random Anime</h2>
    <div v-for="anime in animes" :key="anime.mal_id">
        <p>{{anime.title}}</p>
    </div>
    <h2>Random manga</h2>
    <div v-for="manga in mangas" :key="manga.mal_id">
        <p>{{manga.title}}</p>
    </div>
</template>

<script>

import axios from 'axios';
export default {
    data() {
        return {
            animes: [],
            mangas: [],
            newPost: {
                img :'',
                nombre :''
            }
        };
    },
    async mounted() {
        try {
            const responseAnime = await axios.get('https://api.jikan.moe/v4/random/anime');
            const responseManga = await axios.get('https://api.jikan.moe/v4/random/manga');
            this.mangas = responseManga.data;
            this.animes = responseAnime.data;
            
        } catch (error) {
            console.error(error)
        }
    
    },
}
</script>