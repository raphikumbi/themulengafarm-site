<script setup>
import IconArrowSimple from "./icons/IconArrowSimple.vue";

defineProps({
  href: { type: String, required: true },
  title: { type: String, required: true },
  text: { type: String, required: true },
  actionText: { type: String, required: true },
  icon: { type: Object, required: true }
})
</script>

<template>
  <a :href="href"
     target="_blank"
     rel="noopener noreferrer"
     class="social-card group flex flex-col justify-between bg-white/5 p-8 backdrop-blur-md transition-all duration-300 hover:bg-white/10 hover:border-white/20">

    <div class="flex flex-row justify-between">
      <div>
        <h3 class="text-xl font-bold uppercase tracking-wider text-white">
          {{ title }}
        </h3>
      </div>

      <div class="text-zinc-200 group-hover:text-white transition-colors duration-300">
        <component :is="icon" :size="25" />
      </div>
    </div>


    <div class="mt-5 flex items-center gap-2 text-xs  tracking-wider text-zinc-500 uppercase group-hover:text-white transition-colors duration-300">
      {{ actionText }}
      <IconArrowSimple />
    </div>
  </a>
</template>