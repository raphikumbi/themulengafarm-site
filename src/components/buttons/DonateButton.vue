<script setup>
import IconHeart from "../icons/IconHeart.vue";
</script>

<template>
  <div class="flex justify-center">
    <a
        href="https://donate.raisenow.io/xkmgf"
        class="group flex items-center justify-between bg-accent text-neutral-800 font-bold pl-6 pr-5 h-12.5 w-35 md:w-40 hover:w-42 transition-all duration-300 ease-out"
    >
      <span class="font-bold uppercase tracking-wider translate-y-px text-sm md:text-base text-white">
        Donate
      </span>

      <div class="relative w-5 h-5 flex items-center justify-center">
        <div class="w-5 h-5 stroke-[2.5] transition-all duration-300 ease-out text-white group-hover:scale-110 [&>svg]:fill-transparent group-hover:[&>svg]:fill-white">
          <IconHeart />
        </div>
      </div>
    </a>
  </div>
</template>