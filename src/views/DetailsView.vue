<template>
    <div>
        <router-link :to="{ name: 'Home' }" class="btn btn-primary mb-3">&#8592; Back</router-link>
        <div v-if="error">{{ error }}</div>
        <div v-if="post" class="pokemon">
            <div class="pokemon__head">
                <div class="pokemon__img">
                    <img :src="post.img">
                </div>
                <h3>{{ post.num}} - {{ post.name }}</h3>
            </div>
            <div class="pokemon__body">
                <div class="pokemon__stat">
                    <p><strong>Type(s): </strong>
                        <span v-for="(type, index) in post.type" :key="type">
                            <span v-if="index != 0">, {{ type }}</span>
                                <span v-else>{{ type }}</span>
                        </span>
                    </p>
                </div>
                <div class="pokemon__stat">
                    <p><strong>Height:</strong> {{ post.height }}</p>
                </div>
                <div class="pokemon__stat">
                    <p><strong>Weight:</strong> {{ post.weight }}</p>
                </div>
                <div v-if="post.candy" class="pokemon__stat">
                    <p><strong>Candy:</strong> {{ post.candy }}</p>
                </div>
                <div v-if="post.candy_count" class="pokemon__stat">
                    <p><strong>Candy Count:</strong> {{ post.candy_count }}</p>
                </div>
                <div v-if="post.egg" class="pokemon__stat">
                    <p><strong>Egg:</strong> {{ post.egg }}</p>
                </div>
                <div class="pokemon__stat">
                    <p><strong>Spawn Chance:</strong> {{ post.spawn_chance }}</p>
                </div>
                <div class="pokemon__stat">
                    <p><strong>Spawn Time:</strong> {{ post.spawn_time }}</p>
                </div>
                <div v-if="post.multipliers" class="pokemon__stat">
                    <p><strong>Multiplier(s): </strong>
                        <span v-for="(multiplier, index) in post.multipliers" :key="multiplier">
                            <span v-if="index != 0">, {{ multiplier }}</span>
                                <span v-else>{{ multiplier }}</span>
                        </span>
                    </p>
                </div>
                <div class="pokemon__stat">
                    <p><strong>Weakness: </strong>
                        <span v-for="(weakness, index) in post.weaknesses" :key="weakness">
                            <span v-if="index != 0">, {{ weakness }}</span>
                            <span v-else>{{ weakness }}</span>
                        </span>
                    </p>
                </div>
                <div v-if="post.next_evolution" class="pokemon__stat">
                    <p><strong>Next Evolution(s): </strong>
                        <span v-for="(evolution, index) in post.next_evolution" :key="evolution">
                            <span v-if="index != 0">, {{ evolution.name }}</span>
                            <span v-else>{{ evolution.name }}</span>
                        </span>
                    </p>
                </div>
            </div>
        </div>
    </div>
</template>

<script>
    import getPost from '../composables/getPost';

    export default {
        props: ['id'],
        setup(props) {
            const { post, error, load } = getPost(props.id);

            load();

            return { post, error };
        }
    }
</script>