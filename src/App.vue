<template>
  <main>
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
  </main>
</template>
<script setup>
  // import BreakingBadCards from "./components/BreakingBadCards.vue";
  import RickyMortinsCards from "./components/RickyMortinsCards.vue";
</script>

