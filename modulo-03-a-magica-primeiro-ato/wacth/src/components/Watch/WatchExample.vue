<template>
  <h1>Watch</h1>
  <label><input type="checkbox" v-model="terms" /> Confirmar os termos </label>

  <p>Resultado: {{ result }}</p>
</template>

<script setup>
import { ref, watch } from 'vue'

const terms = ref(0)
const result = ref(null)

watch(terms, () => {
  result.value = 'Pesquisando ...'
  setInterval(() => {
    result.value = 'Aceito'
  }, 3000)
})
</script>
