<script setup>
import { ref, onMounted } from 'vue'
import gsap from 'gsap'
import { ScrollTrigger } from 'gsap/ScrollTrigger'
import SocialCard from "./SocialCard.vue"
import IconEmail from "./icons/IconEmail.vue"
import IconInstagram from "./icons/IconInstagram.vue"
import IconYoutube from "./icons/IconYoutube.vue"

gsap.registerPlugin(ScrollTrigger)

const sectionRef = ref(null)
const cardsRef = ref(null)

const socialChannels = [
  {
    href: 'mailto:lionel.kumbartzki@themulengafarm.org',
    title: 'Email Us',
    text: 'Get in touch for direct questions or general inquiries.',
    actionText: 'Send Message',
    icon: IconEmail
  },
  {
    href: 'https://www.instagram.com/themulengafarm/',
    title: 'Instagram',
    text: 'Periodical updates live from Sambia.',
    actionText: 'Follow Us',
    icon: IconInstagram
  },
  {
    href: 'https://www.youtube.com/@TheMulengaProject-2024',
    title: 'YouTube',
    text: 'In-depth progress updates, news and footage.',
    actionText: 'Watch Videos',
    icon: IconYoutube
  }
]

onMounted(() => {
  gsap.fromTo(
      cardsRef.value.querySelectorAll('.social-card'),
      { opacity: 0, y: 30 },
      {
        opacity: 1,
        y: 0,
        duration: 0.8,
        ease: 'power3.out',
        stagger: 0.12,
        scrollTrigger: {
          trigger: sectionRef.value,
          start: 'top 80%',
        },
      }
  )
})
</script>

<template>
  <section ref="sectionRef" class="py-16 md:py-14">
    <div class="mx-auto max-w-7xl px-6">

      <div class="max-w-3xl mb-14">
        <h2 class="text-4xl font-black tracking-wide text-white md:text-6xl">
          Connect With Us
        </h2>
      </div>

      <div ref="cardsRef" class="grid gap-6 md:grid-cols-3 mb-4">
        <SocialCard
            v-for="channel in socialChannels"
            :key="channel.title"
            v-bind="channel"
        />
      </div>

    </div>
  </section>
</template>