<script setup>
defineProps({
  variant: { type: String, default: 'primary' }, // primary | ghost
  to: { type: [String, Object], default: null }, // lien interne si renseigné
})
</script>

<template>
  <component :is="to ? 'RouterLink' : 'button'" :to="to"
    :class="['btn', 'btn--' + variant]">
    <slot />
  </component>
</template>

<style scoped>
.btn { display: inline-block; padding: var(--space-2) var(--space-4);
  border: 2px solid var(--color-primary); border-radius: var(--radius);
  font: inherit; text-decoration: none; cursor: pointer; }
.btn--primary { background: var(--color-primary);
  color: var(--color-primary-contrast); }
.btn--ghost { background: transparent; color: var(--color-primary); }
</style>