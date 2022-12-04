<template>
  <main>
    <Header 
      :characterShow="characterShow"
      @SelectShow="characterShow = !characterShow"
    />
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
  import { ref } from "vue";
  // import BreakingBadCards from "./components/BreakingBadCards.vue";
  import RickyMortinsCards from "./components/RickyMortinsCards.vue";
  import Header from "./components/Header.vue";

  const characterShow = ref(true);
</script>

