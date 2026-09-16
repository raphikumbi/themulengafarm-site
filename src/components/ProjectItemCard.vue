<script setup>
import { computed } from 'vue'

const props = defineProps({
  title: String,
  description: String,
  current: Number,
  goal: Number
})

const percentage = computed(() => {
  return Math.trunc(props.current / props.goal * 100)
})

const goalReached = props.current === props.goal

</script>

<template>
  <div class="pt-1">
    <div class="p-4 border bg-white border-border-default transition-all duration-300 hover:border-border-hover">

      <div class="mb-2 flex items-start justify-between">
        <div>
          <h3 class="text-lg font-semibold">{{ title }}</h3>
          <p class="mt-1 text-sm text-stone-500">
            {{ description }}
          </p>
        </div>

        <span
            class="rounded-xs px-3 py-1 text-xs font-semibold"
            :class="[
              goalReached ? 'bg-green-100' : 'bg-blue-100' ,
              goalReached ? 'text-green-600' : 'text-secondary'
            ]"
        >
          {{ percentage }}%
        </span>
      </div>

      <div class="mb-2 h-3 overflow-hidden rounded-full bg-stone-100">
        <div
            class="h-full rounded-full"
            :class="goalReached ? 'bg-accent-bright' : 'bg-secondary'"
            :style="{ width: percentage + '%' }"
        />
      </div>

      <div class="flex justify-between text-sm">
        <span class="font-semibold">CHF {{ current.toLocaleString('de-CH') }}</span>
        <span class="text-stone-500">of CHF {{ goal.toLocaleString('de-CH') }}</span>
      </div>

    </div>
  </div>

</template>