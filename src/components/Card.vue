<template>
    <n-card>
        <template #cover>
            <img :src="image">
        </template>
        <h3>{{name}}</h3>
        <slot></slot>
  </n-card>
</template>
<script setup>
    // import {defineProps} from "vue";
    const {image, name} = defineProps(["image", "name",]);
</script>

<style scoped>
p{
    font-size: 12px;
}
</style>