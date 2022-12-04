<template>
  <main>
    <HeaderComp
      :characterShow="characterShow"
      @SelectShow="characterShow = !characterShow"
    />
    <KeepAlive>
      <BreakingBadSuspence v-if="characterShow"/>
      <RickyMortinSuspence v-else/>
    </KeepAlive>
  </main>
</template>
<script setup>
  import { ref } from "vue";
  import BreakingBadSuspence from "./components/BreakingBadSuspence.vue";
  import RickyMortinSuspence from "./components/RickyMortinSuspence.vue";
  import HeaderComp from "./components/HeaderComp.vue";

  const characterShow = ref(true);
</script>

