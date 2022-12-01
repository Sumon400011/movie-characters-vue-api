<template>
    <div>
        <ul>
            <li v-for="char in characters" :key="char.char_id">{{ char.char_id }} :-{{ char.name }}</li>
        </ul>
        <button @click="(page = page - 1)">Prev</button>
        <button @click="page = page + 1">Next</button>
    </div>
</template>
<script setup>
    import axios from "axios";
    import { ref, watch } from "vue";
    const characters = ref(null);
    const page = ref(0);

    const response = await axios.get("https://www.breakingbadapi.com/api/characters?limit=10&offset=0");
    characters.value = response.data;

    watch(page, async () => {
        const res = await axios.get(`https://www.breakingbadapi.com/api/characters?limit=10&offset=${page.value * 10}`);
        characters.value = res.data;
    })

</script>