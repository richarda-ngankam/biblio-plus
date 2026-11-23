<script setup>
import { ref, computed, onMounted } from 'vue'
import SearchBar from '@/components/SearchBar.vue'
import BookList from '@/components/BookList.vue'

const books = ref([])
const query = ref('')

const featured = computed(() =>
  books.value
    .filter(b => b.title.toLowerCase().includes(query.value.toLowerCase()))
    .slice(0, 8))

onMounted(async () => {
  const res = await fetch(import.meta.env.BASE_URL + 'data/books.json')
  books.value = await res.json()
})
</script>

<template>
  <div class="home">
    <section class="hero">
      <h1>Bienvenue à la bibliothèque</h1>
      <SearchBar v-model="query" />
    </section>

    <section aria-labelledby="coeur">
      <h2 id="coeur">Coups de cœur</h2>
      <BookList :books="featured" />
    </section>

    <section aria-labelledby="evenements">
      <h2 id="evenements">Événements</h2>
      <div class="home__placeholder">
        <p>Zone de contenu à remplir</p>
      </div>
    </section>
  </div>
</template>

<style scoped>
.home { max-width: 72rem; margin: 0 auto; padding: var(--space-6);
  display: grid; gap: var(--space-6); }
.hero { background: var(--color-surface); border-radius: var(--radius);
  padding: var(--space-6); text-align: center; }
.hero h1 { margin: 0 0 var(--space-4); }
.home__placeholder { border: 2px dashed var(--color-text);
  border-radius: var(--radius); padding: var(--space-6);
  text-align: center; }
</style>