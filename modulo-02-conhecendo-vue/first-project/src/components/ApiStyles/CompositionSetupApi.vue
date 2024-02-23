<template>Composition Api Setup</template>

<script setup>
import {
  computed,
  onBeforeMount,
  onBeforeUnmount,
  onMounted,
  onUnmounted,
  reactive,
  ref,
  watch
} from 'vue'

const props = defineProps({})

const stateModal = ref(false)

const form = reactive({
  field_1: '',
  field_2: ''
})

const toggleMount = function () {
  stateModal.value = !stateModal.value
}

const fullName = computed(() => {
  return 'First Name' + '' + 'Last Name'
})

const changeStateModal = watch(stateModal, (newValue, oldValue) => {})

onBeforeMount(() => {
  //lifecycle
})

onMounted(() => {
  //lifecycle
})

onBeforeUnmount(() => {
  //lifecycle
})

onUnmounted(() => {
  //lifecycle
})

</script>
