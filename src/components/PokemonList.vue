<template>
  <div class="card-grid">
    <div v-for="post in posts" :key="post.id" class="card">
        <SinglePokemon :post="post" />
    </div>
  </div>
</template>

<script>
import { onMounted, onUnmounted, onUpdated } from 'vue';
import SinglePokemon from './SinglePokemon.vue';

export default {
    props: ['posts'],
    components: { SinglePokemon },
    setup() {

    }
}
</script>

<style>

</style>