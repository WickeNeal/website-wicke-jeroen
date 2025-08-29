<template>
  <nav class="bg-secondary p-4">
    <div class="container mx-auto flex justify-between items-center">
      <a href="#" @click.prevent="scrollTo('hero')" class="text-white text-lg font-bold">
        <svg class="w-8 h-8 inline-block mr-2" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round">
          <path d="M3 9l9-7 9 7v11a2 2 0 0 1-2 2H5a2 2 0 0 1-2-2z"></path>
          <polyline points="9 22 9 12 15 12 15 22"></polyline>
        </svg>
        Jeroen Wicke
      </a>
      <div class="hidden md:flex space-x-4">
        <a href="#features" @click.prevent="scrollTo('features')" class="text-light hover:text-white">Diensten</a>
        <a href="#testimonials" @click.prevent="scrollTo('testimonials')" class="text-light hover:text-white">Testimonials</a>
        <a href="#contact" @click.prevent="scrollTo('contact')" class="text-light hover:text-white">Contact</a>
      </div>
    </div>
  </nav>
</template>

<script setup>
import { useScrollTo } from '../composables/useScrollTo';

const { scrollTo } = useScrollTo();
</script>