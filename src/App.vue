<template>
  <RouterView />
  <div
    v-if="error"
    class="box error"
  >
    An error occurred: {{ error.message }}
  </div>
</template>

<script lang="ts">
import { RouterView } from 'vue-router'

export default {
  name: 'App',
  expose: [],
  components: { RouterView },
  data: () => ({
    error: null as Error|null,
  }),

  errorCaptured (errorCaptured) {
    this.error = errorCaptured as Error
  },
}
</script>
