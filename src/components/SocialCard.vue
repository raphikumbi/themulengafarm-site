<script setup>
defineProps({
  href: { type: String, required: true },
  title: { type: String, required: true },
  text: { type: String, required: true },
  actionText: { type: String, required: true },
  icon: { type: Object, required: true }
})
</script>

<template>
  <a
      :href="href"
      target="_blank"
      rel="noopener noreferrer"
      class="social-card group flex flex-col justify-between rounded-sm border border-white/10 bg-white/5 p-8 backdrop-blur-md transition-all duration-300 hover:bg-white/10 hover:border-white/20"
  >
    <div>

      <div class="mb-6 text-zinc-200 group-hover:text-white transition-colors duration-300">
        <component :is="icon" />
      </div>

      <h3 class="mb-2 text-xl font-bold uppercase tracking-wider text-white">
        {{ title }}
      </h3>
      <p class="text-sm text-zinc-400 leading-relaxed">
        {{ text }}
      </p>
    </div>

    <div class="mt-8 flex items-center gap-2 text-xs font-mono tracking-wider text-zinc-500 uppercase group-hover:text-white transition-colors duration-300">
      {{ actionText }}
      <svg class="h-4 w-4 transform transition-transform duration-300 group-hover:translate-x-1" fill="none" viewBox="0 0 24 24" stroke="currentColor" stroke-width="2">
        <path stroke-linecap="round" stroke-linejoin="round" d="M9 5l7 7-7 7"/>
      </svg>
    </div>
  </a>
</template>