<script setup>

defineProps({
  imgSrc: String,
  name: String,
  func: String,
  loc: String,
  desc: String
});

</script>

<template>
  <div class="team-card flex flex-col items-center space-y-3">
    <img
        :src="imgSrc"
        loading="lazy"
        :alt="name"
        class="w-full h-max object-cover"
    />

    <h3 class="text-lg md:text-2xl font-semibold tracking-wide text-text-strong pt-1">
      {{name}}
    </h3>

    <h3 class="text-sm font-medium text-text-midd -mt-3">
      {{func}}
    </h3>

    <h3 class="text-sm font-light text-text-soft">
      {{loc}}
    </h3>

    <p class="text-sm font-light text-text-soft text-justify">
      {{desc}}
    </p>
  </div>
</template>