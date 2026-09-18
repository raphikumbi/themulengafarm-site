<script setup>

defineProps({
  number: String,
  title: String,
  text: String
});

</script>

<template>
  <div class="relative border border-neutral-200 px-5 pb-4 pt-8">

    <div class="absolute -top-3 left-1/2 -translate-x-1/2 bg-page-bg px-4 text-sm font-semibold  text-accent">
      Goal  {{ number }}
    </div>

    <h3 class="text-center text-lg font-semibold leading-snug text-text-midd">
      {{ title }}
    </h3>

    <p class="mt-4 text-center text-sm leading-6 text-text-soft">
      {{ text }}
    </p>

  </div>
</template>