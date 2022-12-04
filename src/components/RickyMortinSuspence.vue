<template>
    <Suspense>
        <template #default>
            <RickyMortinsCards />
        </template>
        <template #fallback>
            <div>
            <p>Loading.....</p>
            </div>
        </template>
    </Suspense>
</template>
<script setup>
    import RickyMortinsCards from "./RickyMortinsCards.vue";
</script>
