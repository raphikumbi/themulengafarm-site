<script setup>
defineProps({
  title: {
    type: String,
    required: true
  }
})
</script>

<template>
  <h2 class="text-5xl md:text-6xl font-semibold tracking-wide text-[#CFE4C7]">
    {{ title }}
  </h2>
</template>