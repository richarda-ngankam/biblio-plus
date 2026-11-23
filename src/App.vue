<script setup>
import AppHeader from '@/components/AppHeader.vue'
import AppFooter from '@/components/AppFooter.vue'
import HomeView from '@/views/HomeView.vue'
</script>

<template>
  <a class="skip-link" href="#contenu">Aller au contenu</a>
  <AppHeader />
  <main id="contenu" tabindex="-1"><HomeView /></main>
  <AppFooter />
</template>