<script setup>
defineProps({
  src: {
    type: String,
    required: true
  },
  alt: {
    type: String,
    required: true
  }
})
</script>

<template>
  <img
      :src="src"
      :alt="alt"
      class="w-full object-cover select-none"
  />

</template>