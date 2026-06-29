<script setup>
import { ref, computed } from 'vue'
import Home from './Home.vue'
import Contact from './Contact.vue'
import Portfolio from './Portfolio.vue'
import './style.css';

const routes = {
  '/': Home,
  '/contact': Contact,
  '/portfolio': Portfolio
}

const currentRoute = ref(window.location.hash)

window.addEventListener('hashchange', () => {
  currentRoute.value = window.location.hash
})

const currentView = computed(() => {
  return routes[currentRoute.value.slice(1)] || Home
})
</script>

<template>
  <nav>
    <a href="#/" :class="{ active: currentRoute === '#/' }">Home</a>
    <a href="#/portfolio" :class="{ active: currentRoute === '#/portfolio' }">Portfolio</a>
    <a href="#/contact" :class="{ active: currentRoute === '#/contact' }">Contact</a>
  </nav>
  <component :is="currentView" />
</template>
