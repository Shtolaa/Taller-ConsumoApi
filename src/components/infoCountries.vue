<template>
    <h2>Paises</h2>
    <ul>
        <li v-for="post in posts" :key="post.country">
            {{ post.populationCounts}}
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
            const response = await axios.get('https://countriesnow.space/api/v0.1/countries/population');
            this.posts = response.data.data;
            
        } catch (error) {
            console.error(error)
        }
    
    },
}
</script>