<template>
  <section id="contact" class="py-20 bg-light">
    <div class="container mx-auto">
      <div class="grid grid-cols-1 md:grid-cols-2 gap-8">
        <div>
          <h2 class="text-3xl font-bold text-secondary mb-4">Neem contact op</h2>
          <p class="text-secondary mb-4">
            <strong>Adres:</strong> Koolmeeslaan 15, 8900 Ieper<br>
            <strong>Email:</strong> info@wickejeroen.be<br>
            <strong>Telefoon:</strong> +32 479 85 64 09
          </p>
        </div>
        <div>
          <form @submit.prevent="submitForm">
            <div class="mb-4">
              <label for="name" class="block text-secondary font-bold mb-2">Naam *</label>
              <input type="text" id="name" v-model="form.name" class="w-full p-3 border rounded focus:outline-none focus:border-accent focus:ring-1 focus:ring-accent" :class="{ 'border-red-500': errors.name }">
              <p v-if="errors.name" class="text-red-500 text-sm mt-1">{{ errors.name }}</p>
            </div>
            <div class="mb-4">
              <label for="email" class="block text-secondary font-bold mb-2">Email *</label>
              <input type="email" id="email" v-model="form.email" class="w-full p-3 border rounded focus:outline-none focus:border-accent focus:ring-1 focus:ring-accent" :class="{ 'border-red-500': errors.email }">
              <p v-if="errors.email" class="text-red-500 text-sm mt-1">{{ errors.email }}</p>
            </div>
            <div class="mb-4">
              <label for="message" class="block text-secondary font-bold mb-2">Bericht *</label>
              <textarea id="message" v-model="form.message" rows="4" class="w-full p-3 border rounded focus:outline-none focus:border-accent focus:ring-1 focus:ring-accent" :class="{ 'border-red-500': errors.message }"></textarea>
              <p v-if="errors.message" class="text-red-500 text-sm mt-1">{{ errors.message }}</p>
            </div>
            <button type="submit" class="bg-accent text-white px-6 py-3 rounded hover:bg-blue-600">Verzenden</button>
          </form>
        </div>
      </div>
    </div>
  </section>
</template>

<script setup>
import { ref } from 'vue'

const form = ref({
  name: '',
  email: '',
  message: ''
})

const errors = ref({})

const validateEmail = (email) => {
  const re = /^(([^<>()[\]\\.,;:\s@\"]+(\\.[^<>()[\]\\.,;:\s@\"]+)*)|(\".+\"))@((\[[0-9]{1,3}\\.[0-9]{1,3}\\.[0-9]{1,3}\\.[0-9]{1,3}\])|(([a-zA-Z\\-0-9]+\\.)+[a-zA-Z]{2,}))$/
  return re.test(String(email).toLowerCase())
}

const submitForm = () => {
  errors.value = {}

  if (!form.value.name) {
    errors.value.name = 'Naam is verplicht.'
  }
  if (!form.value.email) {
    errors.value.email = 'Email is verplicht.'
  } else if (!validateEmail(form.value.email)) {
    errors.value.email = 'Ongeldig emailadres.'
  }
  if (!form.value.message) {
    errors.value.message = 'Bericht is verplicht.'
  }

  if (Object.keys(errors.value).length === 0) {
    // Handle form submission (e.g., send to an API)
    alert('Formulier verzonden!')
    form.value.name = ''
    form.value.email = ''
    form.value.message = ''
  }
}
</script>
