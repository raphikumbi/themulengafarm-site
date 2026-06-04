<script setup>
defineProps({
  title: {
    type: String,
    required: true
  }
})
</script>

<template>
  <h3 class="text-sm md:text-2xl font-semibold tracking-wide text-[#CFE4C7]">
    {{ title }}
  </h3>
</template>