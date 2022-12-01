<template>
    <n-card>
        <template #cover>
            <img :src="image">
        </template>
        <h3>{{name}}</h3>
        <div class="jobs">
            <p v-for="(job, index) in occupation" :key="index">
                {{job}}<span v-if="(index < occupation.length - 1)">, &nbsp;</span>
            </p>
        </div>
        
  </n-card>
</template>
<script setup>
    // import {defineProps} from "vue";
    const {image, name, occupation} = defineProps(["image", "name", "occupation"]);
</script>

<style scoped>
p{
    font-size: 12px;
}
</style>