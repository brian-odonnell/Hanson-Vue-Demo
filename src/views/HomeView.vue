<template>
    <div class="home">
        <h1 class="mb-5 text-center">Pokémon List</h1>
        <div v-if="error">{{ error }}</div>
        <div v-if="posts.length">
            <PokemonList :posts="posts"/>
        </div>
        <div v-else>Loading...</div>
    </div>
</template>

<script>
import PokemonList from '../components/PokemonList.vue';
import getPosts from '../composables/getPosts';

export default {
    name: 'HomeView',
    components: { PokemonList },
    setup() {
        const { posts, error, load } = getPosts();

        load();

        return { posts, error };
    }
}
</script>
