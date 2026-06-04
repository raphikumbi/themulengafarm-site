<script setup>
import IconHeart from "../icons/IconHeart.vue";
</script>

<template>
  <div class="flex justify-center">
    <a
        href="https://donate.raisenow.io/xkmgf"
        target="_blank"
        rel="noopener noreferrer"
        class="group relative flex items-center justify-between bg-neutral-200 text-neutral-800 font-bold pl-6 pr-5 h-12.5 w-35 md:w-40 hover:w-42 transition-all duration-300 ease-out"
    >
      <span class="font-bold uppercase tracking-wider select-none transform translate-y-px text-sm md:text-base">
        Donate
      </span>

      <div class="relative w-5 h-5 flex items-center justify-center">
        <div class="w-5 h-5 stroke-[2.5] text-neutral-800 transition-all duration-300 ease-out group-hover:scale-110 [&>svg]:fill-transparent group-hover:[&>svg]:fill-neutral-800">
          <IconHeart />
        </div>
      </div>
    </a>
  </div>
</template>