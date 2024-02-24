<template>
  <h1>Computed Properties (OptionsAPI)</h1>
  <input type="text" v-model="userFullNameRename" />

  <p>Nome Completo: {{ user.firstName }} {{ user.lastName }}</p>
  <p>Nome Completo (COMPUTED): {{ userFullName }}</p>
</template>

<script>
export default {
  data() {
    return {
      user: {
        firstName: 'Joab',
        lastName: 'Torres'
      }
    }
  },
  computed: {
    userFullName() {
      return this.user.firstName + ' ' + this.user.lastName
    },
    //fomar de altera
    userFullNameRename: {
      get() {
        return this.user.firstName + ' ' + this.user.lastName
      },
      set(newValue) {
        this.user.firstName = newValue.split(' ')[0]
        this.user.lastName = newValue.split(' ')[1]
      }
    }
  }
}
</script>
