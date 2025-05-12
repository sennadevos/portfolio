<script setup>
import {useI18n} from "vue-i18n";
const { t } = useI18n()
</script>

<template>
  <section id="help" class="p-8 bg-gray-200">
    <h2 class="text-3xl font-semibold mb-6 text-center md:text-right">{{ t('help.title') }}</h2>
    <div class="flex flex-col items-center md:items-end">
      <p class="text-lg text-gray-700 mb-6 max-w-2xl text-center md:text-right">{{ t('help.intro') }}</p>
      <p class="text-lg text-gray-700 mb-6 max-w-2xl text-center md:text-right">{{ t('help.details') }}</p>
      <div class="flex justify-center">
        <a href="mailto:info@sennadevos.com" class="bg-gray-700 text-white py-3 px-6 rounded-lg hover:bg-gray-800 focus:ring-2 focus:ring-gray-500 transition transform hover:scale-105">{{ t('help.cta') }}</a>
      </div>
    </div>
  </section>

</template>