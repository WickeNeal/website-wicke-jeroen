<template>
  <section id="hero" class="bg-cover bg-center h-screen" style="background-image: url('https://images.unsplash.com/photo-1512436991641-6745cdb1723f?ixlib=rb-4.0.3&ixid=MnwxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8&auto=format&fit=crop&w=1770&q=80')">
    <div class="container mx-auto text-center h-full flex flex-col justify-center items-center bg-secondary bg-opacity-50">
      <h1 class="text-5xl font-bold text-white">Jeroen Wicke</h1>
      <p class="text-2xl text-light my-4">Bouw- & renovatiewerken</p>
      <a href="#contact" @click.prevent="scrollTo('contact')" class="bg-accent text-white px-8 py-4 rounded hover:bg-blue-600">Neem contact op</a>
    </div>
  </section>
</template>

<script setup>
import { useScrollTo } from '../composables/useScrollTo';

const { scrollTo } = useScrollTo();
</script>