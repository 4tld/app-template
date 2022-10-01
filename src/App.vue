<template>
  <RouterView />
  <div
    v-if="error"
    class="box error"
  >
    An error occurred: {{ error.message }}
  </div>
</template>

<script setup lang="ts">
import { type Ref, onErrorCaptured, ref } from 'vue'
import { RouterView } from 'vue-router'

const error: Ref<Error|false> = ref(false)

onErrorCaptured((errorCaptured) => {
  error.value = errorCaptured
})
</script>
