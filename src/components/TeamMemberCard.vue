<script setup>

defineProps({
  src: String,
  name: String,
  func: String,
  loc: String,
  desc: String
});
</script>

<template>
  <div class="team-card flex flex-col items-center space-y-3">
    <img
        :src="src"
        loading="lazy"
        :alt="name"
        class="w-80 h-80 object-cover rounded-lg"
    />

    <h3 class="text-lg md:text-2xl font-semibold tracking-wide text-white">
      {{name}}
    </h3>

    <h3 class="text-sm font-medium text-neutral-300 -mt-3">
      {{func}}
    </h3>

    <h3 class="text-sm font-light text-neutral-500 ">
      {{loc}}
    </h3>

    <p class="text-sm text-neutral-400 max-w-xs text-justify">
      {{ desc }}
    </p>
  </div>
</template>