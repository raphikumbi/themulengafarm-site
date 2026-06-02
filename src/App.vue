<script setup>
import { ref, onMounted } from 'vue'
import gsap from 'gsap'
import Header from "./components/Header.vue";
import TitleBanner from "./components/TitleBanner.vue";

const header = ref(null)

const scrollToSection = () => {
  document.getElementById('header')?.scrollIntoView({
    behavior: 'smooth'
  })
}

onMounted(() => {
  gsap.from(header.value, {
    y: -80,
    opacity: 0,
    duration: 1,
    ease: 'power3.out'
  })
})
</script>

<template>
  <div class="min-h-screen bg-neutral-50 text-black">

    <TitleBanner
        image-src="/banner.jpg"
        title="THE MULENGA FARM"
        overlayOpacity="55"
        @scrollToSection="scrollToSection"/>

    <Header id="header"/>

  <main>
    <!-- Your page content -->
  </main>
  </div>
</template>