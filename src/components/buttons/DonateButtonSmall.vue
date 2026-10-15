<script setup>

import { ScrollSmoother } from 'gsap/ScrollSmoother'

const scrollToSupport = () => {
  const smoother = ScrollSmoother.get()
  smoother?.scrollTo('#support', true, '-50px')
}

</script>

<template>
  <div class="flex justify-center">
    <a
        href="#support" @click.prevent="scrollToSupport"
        class="flex justify-center items-center bg-accent h-10 w-20 rounded-[]"
    >
      <span class="font-bold uppercase text-white transform text-xs">
        Donate
      </span>
    </a>
  </div>
</template>