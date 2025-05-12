<script setup>
import {useI18n} from "vue-i18n";
const { t } = useI18n()
</script>

<template>
  <footer class="bg-gray-900 text-gray-300 text-sm text-center p-6">
    <p>&copy; 2025 Senna de Vos Software – {{ t('legal.rightsReserved') }}</p>
    <p>KVK: 97028576 | BTW: NL005244075B09</p>
<!--    <p>-->
<!--      <a href="/algemene-voorwaarden.pdf" class="underline hover:text-white">{{ t('legal.termsAndConditions') }}</a> |-->
<!--      <a href="/privacy-verklaring.pdf" class="underline hover:text-white">{{ t('legal.privacyPolicy') }}</a>-->
<!--    </p>-->
  </footer>
</template>