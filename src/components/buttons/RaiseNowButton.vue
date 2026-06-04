<script setup>
import IconArrow from "../icons/IconArrow.vue";
</script>

<template>
  <div class="flex justify-center">
    <a
        href="https://donate.raisenow.io/xkmgf"
        target="_blank"
        rel="noopener noreferrer"
        class="group relative flex items-center justify-between bg-neutral-200 text-neutral-800 font-bold pl-6 pr-5 h-[50px] w-35 md:w-40 hover:w-48 transition-all duration-300 ease-out overflow-hidden"
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