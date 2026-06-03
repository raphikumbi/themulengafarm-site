<script setup>
import { ref, onMounted } from 'vue'
import gsap from 'gsap'
import Header from "./components/Header.vue";
import OurMission from "./components/OurMission.vue";
import YoutubePlayer from "./components/YoutubePlayer.vue";
import SubTitle from "./components/SubTitle.vue";
import FullScreenPhoto from "./components/FullScreenPhoto.vue";
import SubSubTitle from "./components/SubSubTitle.vue";
import MeetTheTeam from "./components/MeetTheTeam.vue";
import Footer from "./components/Footer.vue";
import TitleBanner from "./components/TitleBanner.vue";

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

  gsap.fromTo(
      teamSection.value,
      {
        opacity: 0,
        x: -80,
      },
      {
        opacity: 1,
        x: 0,
        duration: 1,
        ease: 'power3.out',
        scrollTrigger: {
          trigger: teamSection.value,
          start: 'top 80%',
          toggleActions: 'play none none none',
        },
      }
  )
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
      <YoutubePlayer thumbnail="/video/banner-2025-christmas.jpg" title="Updates 2025" id="75ftg_fsrLQ" duration="3:00" width="100%" height="400px"/>

      <div class="px-5 py-10">
        <SubSubTitle title="Infrastructure Development and Agricultural Expansion Progress" />

        <div class="text-neutral-400 pbs-5 ">
          <ul class="list-disc pl-5 text-neutral-400">
            <li>Continued construction of training center (classrooms, doors, facilities)</li>
            <li>Expansion of water system, including setup for irrigation (water tank planned)</li>
            <li>Sanitation system connected and improved</li>
            <li>Ongoing planting of fruit trees (citrus, avocados, bananas)</li>
            <li>Preparation for 2026 expansion to larger farmland</li>
            <li>Future needs include fencing, irrigation, and full farm infrastructure</li>
          </ul>
        </div>

      </div>
    </div>


    <FullScreenPhoto alt="farm" src="/farm-peoples-1500.jpg" />
  </div>

  <div class="min-h-screen bg-[#171717] text-black">

    <br>
    <br>

    <div class="mx-auto max-w-7xl px-4 py-2">
      <div ref="teamSection" class="px-5 py-10">
        <h1 class="text-4xl md:text-7xl font-semibold tracking-wide text-white">
          Meet the team
        </h1>
      </div>
    </div>

    <MeetTheTeam />

    <br>
    <br>

    <Footer />
  </div>
</template>