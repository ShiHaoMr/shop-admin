<script setup>
import { ref } from 'vue'

defineProps({
  msg: String,
})

const count = ref(0)
</script>

<template>
  <button class="btn">按钮</button>
</template>

<style scoped>
.read-the-docs {
  color: #888;
}

.btn {
  @apply bg-red-600 p-2 py-1 text-light-900 rounded-lg;
}
</style>
