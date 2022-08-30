<template>
    <router-link :to="{ name: 'Details', params: { id: post.id }}" class="card__link">
        <div class="card__img">
            <img :src="post.img">
        </div>
        <h3 class="card__headline">{{ post.num}} - {{ post.name }}</h3>
        <ul class="card__types">
            <li v-for="type in post.type" :key="type">{{ type }}</li>
        </ul>
    </router-link>
</template>

<script>

export default {
    props: ['post'],
    setup() {
    }
}
</script>