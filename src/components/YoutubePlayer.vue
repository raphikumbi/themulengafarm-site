<script setup>
import { ref } from 'vue'

const props = defineProps({
  id: { type: String, required: true },
  title: { type: String, required: true },
  thumbnail: { type: String, required: true },
  duration: { type: String, default: '5:00' }
})

const isPlaying = ref(false)
</script>

<template>
  <div class="w-full max-w-4xl mx-auto my-6">

    <button
        v-if="!isPlaying"
        @click="isPlaying = true"
        :style="{ backgroundImage: `url(${thumbnail})` }"
        class="group relative w-full h-48 sm:h-64 bg-cover bg-center rounded-2xl overflow-hidden flex flex-col justify-between p-6 text-left shadow-xl border border-slate-800 transition-transform duration-300 active:scale-[0.99]"
    >
      <div class="absolute inset-0 bg-gradient-to-t from-slate-950/90 via-slate-950/50 to-slate-950/40 z-0"></div>

      <div class="relative z-10 w-full h-full flex flex-col justify-between items-start">

        <div class="my-auto max-w-xl">
          <h3 class="text-xl sm:text-2xl font-bold text-white tracking-tight drop-shadow-md group-hover:text-emerald-400 transition-colors duration-300">
            {{ title }}
          </h3>
        </div>

        <div class="w-full flex items-center justify-between mt-auto">

          <div class="flex items-center gap-2 px-4 py-2 bg-slate-900/80 border border-slate-800 rounded-lg backdrop-blur-sm text-sm font-semibold text-slate-200 transition-all duration-300 group-hover:bg-emerald-500 group-hover:text-slate-950 group-hover:border-emerald-400 hover:!bg-emerald-400">
            <svg class="w-4 h-4 fill-current" viewBox="0 0 24 24">
              <path d="M8 5v14l11-7z"/>
            </svg>
            <span>Play</span>
          </div>

          <div class="px-3 py-2 bg-slate-900/80 border border-slate-800 rounded-lg backdrop-blur-sm text-xs font-mono text-slate-400 transition-all duration-300 group-hover:bg-emerald-500 group-hover:text-slate-950 group-hover:border-emerald-400 hover:!bg-emerald-400">
            {{ duration }}
          </div>

        </div>
      </div>
    </button>

    <div v-else class="relative w-full aspect-video bg-black rounded-2xl overflow-hidden shadow-2xl border border-slate-800">
      <iframe
          class="absolute top-0 left-0 w-full h-full"
          :src="`https://www.youtube.com/embed/${id}?autoplay=1`"
          title="YouTube video player"
          allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture"
          allowfullscreen
      ></iframe>
    </div>

  </div>
</template>