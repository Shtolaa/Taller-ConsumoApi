<template>
    <h2>Recomendacion Anime</h2>
    <ul>
        <li v-for="post in posts" :key="post.mal_id">
            {{ post.title}}
        </li>
    </ul>
</template>

<script>

import axios from 'axios';
export default {
    data() {
        return {
            posts: []
        };
    },
    async mounted() {
        try {
            const response = await axios.get('https://api.jikan.moe/v4/recommendations/anime');
            this.posts = response.data;
            
        } catch (error) {
            console.error(error)
        }
    
    },
}
</script>