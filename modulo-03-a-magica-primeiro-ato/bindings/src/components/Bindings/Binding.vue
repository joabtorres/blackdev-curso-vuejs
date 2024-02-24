<template>
  <h1>Bindings</h1>
  <input :type="input.type" :name="input.name" v-bind:placeholder="input.placeholder" />

  <button @click="showPassword">Mostrar / Ocutar senha</button>
</template>

<script setup>
import { reactive } from 'vue'

const input = reactive({
  name: 'password',
  type: 'password',
  placeholder: 'Digite sua senha'
})

const showPassword = function () {
  if (input.type === 'password') {
    input.type = 'text'
  } else {
    input.type = 'password'
  }
}
</script>
