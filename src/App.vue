<script setup>
import { ref, onMounted } from 'vue'
import gsap from 'gsap'
import Header from "./components/Header.vue";
import TitleBanner from "./components/TitleBanner.vue";
import OurMission from "./components/OurMission.vue";
import YoutubePlayer from "./components/YoutubePlayer.vue";
import SubTitle from "./components/SubTitle.vue";

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
  <div class="min-h-screen bg-[#161B17] text-black">

    <TitleBanner
        image-src="/banner.jpg"
        title="THE MULENGA FARM"
        overlayOpacity="55"
        @scrollToSection="scrollToSection"
    />

    <Header id="header"/>

    <div class="mx-auto max-w-7xl px-4">
      <OurMission />
    </div>

    <hr class="border-neutral-600" />

    <div class="mx-auto max-w-7xl px-4 py-2">

      <div class="px-5 py-10">
        <SubTitle title="Latest Updates from Sambia" />
      </div>

      <YoutubePlayer thumbnail="/banner.jpg" title="Updates 2025" id="75ftg_fsrLQ" duration="3:00" width="100%" height="400px"/>
    </div>

    <br>
    <br>

  </div>
</template>