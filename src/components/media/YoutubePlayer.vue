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
  <div>
    <button
        @click="isPlaying = true"
        :style="{
        backgroundImage: `url(${thumbnail})`,
        width,
        height
      }"
        class="group relative bg-cover bg-center rounded-custom overflow-hidden p-6 text-left transition-transform duration-300 active:scale-[0.99] cursor-pointer">

      <div class="absolute inset-0 bg-linear-to-t from-neutral-950/85 to-neutral-950/20 z-0"></div>

      <div class="relative z-10 h-full flex items-end justify-between">

        <div class="flex flex-col gap-5">

          <h3 class="pb-2 md:text-8xl text-5xl font-bold text-white">
            {{ title }}
          </h3>

          <div class="flex items-center px-6 w-28 h-12 gap-3 bg-white text-m font-semibold text-black transition-all duration-300 group-hover:w-35 justify-between">
            <span>Play</span>
            <div class="w-5 h-5 stroke-[1.25] text-black">
              <IconPlay />
            </div>
          </div>

        </div>

        <div class="px-3 py-2 bg-neutral-800 text-xs font-mono text-neutral-200">
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
            class="absolute -top-12 right-0 text-white text-4xl font-light hover:text-zinc-200 cursor-pointer"
        >
          ×
        </button>

        <div
            class="relative aspect-video"
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