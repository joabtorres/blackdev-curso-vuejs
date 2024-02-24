<template>
  <h1>Watch</h1>
  <label><input type="checkbox" v-model="form.terms" /> Confirmar os termos </label>

  <p>Resultado: {{ form.status }}</p>
</template>
<script setup>
import { reactive, watch } from 'vue'

const form = reactive({
  terms: false,
  status: null
})

watch(
  () => form.terms,
  (newValue) => {
    if (newValue) {
      form.status = 'Aceito'
    } else {
      form.status = 'Recusado'
    }
  }
)
</script>
