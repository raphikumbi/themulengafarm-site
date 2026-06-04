<script setup>
import { ref } from 'vue'
import IconPlay from "../icons/IconPlay.vue";

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

      <div class="absolute inset-0 bg-linear-to-t from-neutral-950/75 to-neutral-950/40 z-0"></div>

      <div class="relative z-10 h-full flex items-end justify-between">

        <div class="flex flex-col gap-5">

          <h3 class="text-2xl sm:text-3xl font-bold text-white tracking-tight drop-shadow-md">
            {{ title }}
          </h3>

          <div class="self-start min-w-25 min-h-12.5 flex items-center gap-2 px-7 py-2 bg-neutral-200 backdrop-blur-sm text-m font-semibold text-neutral-800 transition-all duration-300 group-hover:bg-white group-hover:text-slate-950">
            <span>Play</span>

            <div class="w-5 h-5 stroke-[1.5] text-neutral-800 transition-all duration-300 ease-out group-hover:scale-110">
              <IconPlay />
            </div>
          </div>

        </div>

        <div class="px-3 py-2 bg-neutral-800 backdrop-blur-sm text-xs font-mono text-neutral-200">
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