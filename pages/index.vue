<template>
    <header>
      <div class="container">
        <NuxtLogo />
        <h1 class="h1">Accueil</h1>
        <Navigation />
      </div>
    </header>
</template>

<script>
import NuxtLogo from '@/components/NuxtLogo.vue';
import Navigation from '@/components/Navigation.vue';
export default {
  name: 'IndexPage',
}
</script>

<style scoped>

header > div > h1.h1{
  font-size: 2.5rem;
  margin-bottom: 1rem;
  text-align:center;
}
</style>
