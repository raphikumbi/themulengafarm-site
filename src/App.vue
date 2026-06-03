<script setup>
import { ref, onMounted } from 'vue'
import gsap from 'gsap'
import Header from "./components/Header.vue";
import TitleBanner from "./components/TitleBanner.vue";
import OurMission from "./components/OurMission.vue";
import YoutubePlayer from "./components/YoutubePlayer.vue";

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
        @scrollToSection="scrollToSection"
    />

    <Header id="header"/>

    <OurMission />

    <YoutubePlayer thumbnail="/banner.jpg" title="Updates 2025" id="75ftg_fsrLQ" duration="3:00"/>

    <br>
    <br>

  </div>
</template>