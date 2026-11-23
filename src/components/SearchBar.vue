<script setup>
import BaseButton from './BaseButton.vue'
const model = defineModel({ type: String, default: '' })
</script>

<template>
  <form class="search" role="search" @submit.prevent>
    <label for="q" class="sr-only">Rechercher un livre</label>
    <input id="q" v-model="model" type="search"
      placeholder="Titre, auteur…" />
    <BaseButton type="submit">Rechercher</BaseButton>
  </form>
</template>

<style scoped>
.search { display: flex; justify-content: center; gap: var(--space-2); }
.search input { padding: var(--space-2) var(--space-4);
  border: 1px solid var(--color-text); border-radius: var(--radius);
  font: inherit; min-width: 16rem; }
</style>