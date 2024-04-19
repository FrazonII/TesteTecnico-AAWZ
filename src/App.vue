<script setup>
import Forms from './components/Forms.vue'
</script>

<template>

  <main>
     <Forms />
  </main>

</template>

<style scoped>

@media (min-width: 1024px) {
  header {
    display: flex;
    place-items: center;
    padding-right: calc(var(--section-gap) / 2);
  }

}
</style>
