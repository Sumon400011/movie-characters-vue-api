<template>
    <div class="container">
        <div class="cards">
            <Card 
                v-for="char in characters"
                :key="char.char_id"
                :image="char.img"
                :name="char.name"
            >
            <div class="jobs">
                <p v-for="(job, index) in char.occupation" :key="index">
                    {{job}}<span v-if="(index < char.occupation.length - 1)">, &nbsp;</span>
                </p>
            </div>
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
    import { ref, watch } from "vue";
    import Card from "./Card.vue"
    const characters = ref(null);
    const page = ref(0);

    const response = await axios.get("https://www.breakingbadapi.com/api/characters?limit=8&offset=0");
    characters.value = response.data;

    watch(page, async () => {
        const res = await axios.get(`https://www.breakingbadapi.com/api/characters?limit=8&offset=${page.value * 8}`);
        characters.value = res.data;
    })

</script>