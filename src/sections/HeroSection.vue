<script setup>
import heroImage from "../assets/hero_image.jpg"

import {useI18n} from "vue-i18n";
const { t } = useI18n()
</script>

<template>
  <section class="flex flex-col md:flex-row items-center justify-center min-h-screen p-8 bg-gray-200">
    <img :src="heroImage" alt="profile image" class="w-48 h-48 object-cover rounded-lg mb-6 md:mb-0 md:mr-10" />
    <div class="text-center md:text-left">
      <h1 class="text-3xl font-bold">Senna de Vos</h1>
      <h2 class="text-xl text-gray-600 mb-4">{{ t('title') }}</h2>
      <div class="flex justify-center md:justify-start space-x-4">
        <a href="https://linkedin.com/in/senna-de-vos" class="text-gray-600 hover:text-black">LinkedIn</a>
        <a href="https://github.com/sennadevos" class="text-gray-600 hover:text-black">GitHub</a>
      </div>
    </div>
  </section>
</template>