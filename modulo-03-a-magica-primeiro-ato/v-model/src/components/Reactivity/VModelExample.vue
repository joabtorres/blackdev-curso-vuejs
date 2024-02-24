<template>
  <h1>Utilizando v-model</h1>

  <p>Nome: {{ form.name }}</p>

  <form @submit.prevent="submitForm">
    <label for="name">name</label><br />
    <input type="text" id="name" v-model="form.name" /> <br />
    <label for="email">email</label><br />
    <input type="text" id="email" v-model="form.email" /> <br />
    <label for="password">password</label><br />
    <input type="password" id="password" v-model="form.password" /> <br />
    <button type="submit">Salvar</button>
  </form>
</template>

<script setup>
import { reactive } from 'vue'

const form = reactive({
  name: 'joab',
  email: '',
  password: ''
})

const submitForm = () => {
  console.log(form.name, form.email, form.password)
}
</script>
