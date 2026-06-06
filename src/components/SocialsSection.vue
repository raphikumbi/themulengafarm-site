<script setup>
import { ref, onMounted, onBeforeUpdate } from 'vue'
import gsap from 'gsap'
import { ScrollTrigger } from 'gsap/ScrollTrigger'
import SocialCard from "./SocialCard.vue"
import IconEmail from "./icons/IconEmail.vue"
import IconInstagram from "./icons/IconInstagram.vue"
import IconYoutube from "./icons/IconYoutube.vue"

gsap.registerPlugin(ScrollTrigger)

const sectionRef = ref(null)
const cardElements = ref([])

onBeforeUpdate(() => {
  cardElements.value = []
})

const socialChannels = [
  {
    href: 'mailto:lionel.kumbartzki@themulengafarm.org',
    title: 'Email',
    text: 'Get in touch for direct questions or general inquiries.',
    actionText: 'Contact Us',
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
  const targets = cardElements.value
      .filter(Boolean)
      .map(card => card.$el || card)

  if (targets.length > 0) {
    gsap.fromTo(targets,
        {
          opacity: 0,
          yPercent: 40
        },
        {
          opacity: 1,
          yPercent: 0,
          duration: 0.5,
          ease: "power3.out",
          stagger: 0.2,
          clearProps: "transform",
          scrollTrigger: {
            trigger: sectionRef.value,
            start: "top 75%",
            toggleActions: "play none none none",
            once: true
          }
        }
    );
  }
})
</script>

<template>
  <section ref="sectionRef" class="py-12 md:py-14">
    <div class="mx-auto max-w-7xl px-6 overflow-hidden">

      <div class="max-w-3xl mb-14">
        <h2 class="text-4xl font-black tracking-wide text-white md:text-6xl text-center md:text-start">
          Connect With Us
        </h2>
      </div>

      <div class="grid gap-6 md:grid-cols-3 mb-4">
        <SocialCard
            v-for="(channel, index) in socialChannels"
            :key="channel.title"
            :ref="el => { if (el) cardElements[index] = el }"
            v-bind="channel"
        />
      </div>

    </div>
  </section>
</template>