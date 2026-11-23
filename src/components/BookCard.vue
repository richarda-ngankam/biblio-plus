<script setup>
defineProps({
  book: { type: Object, required: true },
  favorite: { type: Boolean, default: false },
})
const emit = defineEmits(['toggle-favorite'])
</script>

<template>
  <article class="book-card">
    <img class="book-card__cover" :src="book.cover" width="200" height="300"
      :alt="'Couverture de ' + book.title" loading="lazy" />
    <div class="book-card__body">
      <h3 class="book-card__title">{{ book.title }}</h3>
      <p class="book-card__author">{{ book.author }}</p>
      <p class="book-card__status"
        :class="{ 'book-card__status--off': !book.available }">
        {{ book.available ? 'Disponible' : 'Emprunté' }}
      </p>
      <button class="book-card__fav" type="button"
        :aria-pressed="favorite"
        @click="emit('toggle-favorite', book.id)">
        {{ favorite ? '★ Retirer des favoris' : '☆ Ajouter aux favoris' }}
      </button>
      <slot name="actions" />
    </div>
  </article>
</template>

<style scoped>
.book-card { background: var(--color-surface); border-radius: var(--radius);
  padding: var(--space-4); box-shadow: 0 1px 4px rgba(0, 0, 0, 0.12); }
.book-card__cover { display: block; width: 100%; aspect-ratio: 2 / 3;
  object-fit: cover; background: var(--color-bg);
  border-radius: var(--radius); }
.book-card__body { margin-top: var(--space-2); }
.book-card__title { font-size: var(--fs-300); margin: 0; }
.book-card__author { margin: 0; }
.book-card__status { margin: var(--space-2) 0; font-weight: 700;
  color: var(--color-primary); }
.book-card__status--off { color: var(--color-danger); }
.book-card__fav { width: 100%; padding: var(--space-2);
  background: var(--color-surface); color: var(--color-primary);
  border: 2px solid var(--color-primary); border-radius: var(--radius);
  font: inherit; cursor: pointer; }
</style>