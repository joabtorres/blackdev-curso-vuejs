<template>
  <h1>Computed Properties (Composition API)</h1>
  <input type="text" v-model="fullNameRename" />

  <p>Nome completo: {{ user.firstName }} {{ user.lastName }}</p>
  <p>Nome Completo (COMPUTED): {{ fullName }}</p>
</template>

<script setup>
import { computed, reactive } from 'vue'

const user = reactive({
  firstName: 'Joab',
  lastName: 'Torres'
})

/**
 * Forma de computar (juntar) varios valores reativos
 */
const fullName = computed(() => {
  return user.firstName + ' ' + user.lastName
})

/**
 * Forma computar ou alterar vários valores reativos computados
 */

const fullNameRename = computed({
  get() {
    return user.firstName + ' ' + user.lastName
  },
  set(newValue) {
    user.firstName = newValue.split(' ')[0]
    user.lastName = newValue.split(' ')[1]
  }
})
</script>
