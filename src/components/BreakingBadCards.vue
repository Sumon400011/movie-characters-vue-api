<template>
    <div>
        {{response.data}}
    </div>
</template>
<script setup>
    import axios from "axios";
    const response = await axios.get("https://www.breakingbadapi.com/api/characters");
</script>