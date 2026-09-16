<script setup>
import IconArrow from "../icons/IconArrow.vue";
</script>

<template>
  <div class="flex justify-center">
    <a
        href="https://donate.raisenow.io/xkmgf"
        target="_blank"
        rel="noopener noreferrer"
        class="group relative flex items-center justify-between bg-accent text-white font-bold pl-6 pr-5 h-12.5 w-35 md:w-40 hover:w-45 transition-all duration-300 ease-out overflow-hidden"
    >
      <span class="font-bold uppercase tracking-wider select-none transform translate-y-px text-sm md:text-base">
        Donate
      </span>

      <div class="relative flex h-5 w-8 items-center justify-center transition-transform duration-300 ease-out group-hover:translate-x-1">
        <IconArrow />
      </div>
    </a>
  </div>
</template>