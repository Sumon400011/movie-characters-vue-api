<template>
    <div class="container">
        <div class="cards">
            <Card 
                v-for="char in characters"
                :key="char.id"
                :image="char.image"
                :name="char.name"
            >
                <p>{{char.location.name}}</p>
            </Card>
        </div>
        <div class="button-container">
            <button @click="page = page - 1">&lt;</button>
            <button @click="page = page + 1">></button>
        </div>
    </div>
</template>
<script setup>
    import axios from "axios";
    import { ref, watch, onMounted } from "vue";
    import Card from "./Card.vue";
    const characters = ref(null);
    const page = ref(1);

    onMounted(async () => {
        const response = await axios.get("https://rickandmortyapi.com/api/character/?page=1");
        characters.value = response.data.results;
    });

    watch(page, async () => {
        const res = await axios.get(`https://rickandmortyapi.com/api/character/?page=${page.value}`);
        characters.value = res.data.results;
    })

</script>