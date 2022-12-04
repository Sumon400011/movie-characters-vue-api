<template>
    <div style="text-align: center; padding: 30px 20px;">
        <h1>{{ characterShow ? 'Breaking Bad' : 'Ricky and Mortins' }}</h1>
        <p @click="emitSelectedShow">{{ characterShow ? 'Ricky and Mortins' : 'Breaking Bad' }}</p>
    </div>
</template>
<script setup>
    import { defineEmits } from 'vue';
    const { characterShow } = defineProps(["characterShow"]);
    const emit = defineEmits(["SelectShow"]);
    const emitSelectedShow = () => {
        emit("SelectShow", characterShow);
    }
</script>
  
<style scoped>
h1{
    font-weight: bold;
    margin-bottom: 20px;
}
p{
    font-size: 16px!important;
    cursor: pointer;
    font-weight: 600;
}
</style>