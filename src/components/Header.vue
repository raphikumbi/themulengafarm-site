<script setup>
import DonateButton from './buttons/DonateButton.vue'
import DonateButtonSmall from "./buttons/DonateButtonSmall.vue";
</script>

<template>
  <header class="flex items-center justify-between px-6 py-4 sticky top-0 z-50 bg-zinc-50 border-b border-border-default">
    <div class="flex items-center gap-3">

      <img
          src="/logo-96.png"
          alt="Logo"
          class="h-12 w-12 object-cover rounded-full"
      />

      <h1 class="text-xl md:text-3xl font-jakarta font-semibold tracking-wider text-black">
        THE MULENGA FARM
      </h1>

    </div>

    <div class="hidden md:block">
      <DonateButton />
    </div>

    <div class="block md:hidden">
      <DonateButtonSmall />
    </div>

  </header>
</template>