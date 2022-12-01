<template>
    <n-card title="Card with Cover">
        <template #cover>
            <img :src="image">
        </template>
        <h3>{{name}}</h3>
        <p v-for="(job, index) in occupation" :key="index">
            {{job}} <span v-if="(index < occupation.length - 1)">,&npsb</span>
        </p>
  </n-card>
</template>
<script setup>
    // import {defineProps} from "vue";
    const {image, name, occupation} = defineProps(["image", "name", "occupation"]);
</script>