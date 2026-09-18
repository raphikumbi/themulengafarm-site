<script setup>
import DonateButton from './buttons/DonateButton.vue'
import DonateButtonSmall from "./buttons/DonateButtonSmall.vue";
</script>

<template>
  <header class="flex items-center justify-between px-4 py-2 min-[450px]:px-6 min-[450px]:py-4 sticky top-0 z-50 bg-zinc-50 border-b border-border-default">
    <div class="flex items-center gap-3">

      <img
          src="/logo-96.png"
          alt="Logo"
          class="h-12 w-12 object-cover rounded-full"
      />

      <h1 class="text-sm min-[450px]:text-xl sm:text-3xl font-jakarta font-semibold tracking-wider text-black">
        THE MULENGA FARM
      </h1>

    </div>

    <div class="hidden min-[450px]:block">
      <DonateButton />
    </div>

    <div class="block min-[450px]:hidden">
      <DonateButtonSmall />
    </div>

  </header>
</template>