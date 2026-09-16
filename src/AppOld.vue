<script setup>
import { ref, onMounted } from 'vue'
import gsap from 'gsap'
import Header from "./components/Header.vue";
import OurMission from "./components/OurMission.vue";
import YoutubePlayer from "./components/media/YoutubePlayer.vue";
import SubTitle from "./components/text/SubTitle.vue";
import FullScreenPhoto from "./components/media/FullScreenPhoto.vue";
import SubSubTitle from "./components/text/SubSubTitle.vue";
import MeetTheTeam from "./components/MeetTheTeam.vue";
import Footer from "./components/Footer.vue";
import TitleBanner from "./components/TitleBanner.vue";
import SupportUs from "./components/SupportUs.vue";
import SocialsSection from "./components/SocialsSection.vue";
import SeparationLine from "./components/icons/SeparationLine.vue";

const header = ref(null)
const teamSection = ref(null)

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
  <div class="min-h-screen bg-[#161D19] text-black">

    <TitleBanner
        image-src="/banner.jpg"
        title="THE MULENGA FARM"
        overlayOpacity="35"
        @scrollToSection="scrollToSection"
    />

    <Header id="header"/>

    <div class="mx-auto max-w-7xl px-4 pb-2">
      <OurMission />
    </div>

    <p class="text-2xl text-zinc-100">PICTURES of main points and make emotional connection</p>

    <SeparationLine />

    <div class="mx-auto max-w-7xl px-4 pt-8 pb-8">
      <div class="px-5 py-10 pb-12">
        <SubTitle title="Latest Updates from Zambia" />
      </div>
      <YoutubePlayer thumbnail="/video/banner-2025-christmas.jpg" title="Updates 2025" id="75ftg_fsrLQ" duration="3:00" width="100%" height="400px"/>

      <div class="px-5 py-10 pt-15">
        <SubSubTitle title="Infrastructure Development and Agricultural Expansion Progress" />

        <div class="py-5">
          <ul class="list-disc pl-5 text-zinc-200">
            <li>Expansion of water system, including setup for irrigation</li>
            <li>Sanitation system connected</li>
            <li>Ongoing planting of fruit trees (citrus, avocados, bananas)</li>
            <li>Preparation for expansion to larger farmland</li>
            <li>Legal procedures for NGO structures in Zambia</li>
          </ul>
        </div>

        <SubSubTitle title="Next Steps 2026" />

        <div class="py-5">
          <ul class="list-disc pl-5 text-zinc-200">
            <li>Legal procedures for NGO structures in Zambia</li>
            <li>Improvements of the community training center</li>
            <li>Enquiries for farmlands</li>
            <li>Farming and training activities</li>
          </ul>
        </div>

      </div>
    </div>


    <FullScreenPhoto alt="farm" src="/farm-peoples-1500.jpg" />


    <div class="min-h-screen bg-[#191919] text-black">

      <SupportUs />

      <SeparationLine />

      <SocialsSection />

      <SeparationLine />

      <div class="mx-auto max-w-7xl px-4 py-2">
        <div class="px-5 pt-14 pb-7">
          <h2 class="mb-6 text-4xl font-black tracking-wide text-white md:text-7xl">
            Meet the Team
          </h2>
        </div>
      </div>

      <MeetTheTeam />

      <br>
      <br>

      <Footer />
    </div>
  </div>
</template>