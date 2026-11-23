
<template>
  <footer class="app-footer">
    <p>Bibliothèque municipale — ouvert du mardi au samedi</p>
    <RouterLink to="/contact">Contact</RouterLink>
  </footer>
</template>

<style scoped>
.app-footer { display: flex; justify-content: space-between;
  align-items: center; padding: var(--space-4) var(--space-6);
  background: var(--color-surface); }
.app-footer p { margin: 0; }
.app-footer a { color: var(--color-primary); }
</style>