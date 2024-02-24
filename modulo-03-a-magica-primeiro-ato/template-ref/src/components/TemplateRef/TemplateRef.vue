<template>
  <h1>Template Ref</h1>
  <p id="welcome" ref="welcome">Olá mundo</p>
</template>

<script setup>
import { onMounted, ref } from 'vue'

const welcome = ref(null)

onMounted(() => {
  welcome.value.style.color = 'red'

  console.log(welcome.value)
})
</script>
