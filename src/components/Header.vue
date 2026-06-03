<script setup>
import DonateButton from './DonateButton.vue'
</script>

<template>
  <header class="flex items-center justify-between px-6 py-4 sticky top-0 z-50 bg-[#161B17] backdrop-blur-md border-b border-b-neutral-600">

    <div class="flex items-center gap-3">
      <img
          src="/logo-96.png"
          alt="Logo"
          class="h-12 w-12 object-cover rounded-full"
      />
      <h1 class="text-1xl md:text-4xl font-sans font-semibold tracking-wider text-[#CFE4C7]">
        THE MULENGA FARM
      </h1>
    </div>

    <DonateButton />

  </header>
</template>