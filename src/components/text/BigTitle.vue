<script setup>
defineProps({
  title: {
    type: String,
    required: true
  }
})
</script>

<template>
  <h1 class="text-5xl md:text-7xl font-semibold tracking-wide text-[#CFE4C7]">
    {{ title }}
  </h1>
</template>