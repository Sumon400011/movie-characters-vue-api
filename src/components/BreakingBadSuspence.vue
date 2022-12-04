<template>
    <Suspense>
        <template #default>
            <BreakingBadCards />
        </template>
        <template #fallback>
            <div>
            <p>Loading.....</p>
            </div>
        </template>
    </Suspense>
</template>
<script setup>
    import BreakingBadCards from "./BreakingBadCards.vue";
</script>
