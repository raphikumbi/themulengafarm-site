<script setup>
import { ref } from 'vue'

defineProps({
  id: { type: String, required: true },
  title: { type: String, required: true },
  thumbnail: { type: String, required: true },
  duration: { type: String, default: '5:00' },

  width: {
    type: String,
    default: '40rem'
  },

  height: {
    type: String,
    default: '16rem'
  }
})

const isPlaying = ref(false)
</script>

<template>
  <div class="px-5">

    <button
        @click="isPlaying = true"
        :style="{
        backgroundImage: `url(${thumbnail})`,
        width,
        height
      }"
        class="group relative bg-cover bg-center rounded-[10px] overflow-hidden p-6 text-left shadow-xl  transition-transform duration-300 active:scale-[0.99] cursor-pointer">

      <div class="absolute inset-0 bg-linear-to-t from-neutral-950/40 to-neutral-950/20 z-0"></div>

      <div class="relative z-10 h-full flex items-end justify-between">

        <div class="flex flex-col gap-5">

          <h3 class="text-xl sm:text-2xl font-bold text-white tracking-tight drop-shadow-md">
            {{ title }}
          </h3>

          <div class="self-start flex items-center gap-2 px-4 py-2 bg-neutral-200 rounded-lg backdrop-blur-sm text-sm font-semibold text-neutral-800 transition-all duration-300 group-hover:bg-green-500 group-hover:text-slate-950">
            <span>Play</span>

            <svg class="w-4 h-4 fill-current" viewBox="0 0 24 24">
              <path d="M8 5v14l11-7z" />
            </svg>
          </div>

        </div>

        <div class="px-3 py-2 bg-neutral-800 rounded-lg backdrop-blur-sm text-xs font-mono text-neutral-200">
          {{ duration }}
        </div>

      </div>
    </button>

    <div
        v-if="isPlaying"
        class="fixed inset-0 z-50 flex items-center justify-center bg-black/80 p-4"
        @click.self="isPlaying = false"
    >
      <div class="relative w-full max-w-5xl">

        <button
            @click="isPlaying = false"
            class="absolute -top-12 right-0 text-white text-4xl font-light hover:text-green-500 cursor-pointer"
        >
          ×
        </button>

        <div
            class="relative w-full aspect-video bg-black rounded-2xl overflow-hidden shadow-2xl"
        >
          <iframe
              class="absolute inset-0 w-full h-full"
              :src="`https://www.youtube.com/embed/${id}?autoplay=1`"
              title="YouTube video player"
              allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture"
              allowfullscreen
          />
        </div>

      </div>
    </div>

  </div>
</template>