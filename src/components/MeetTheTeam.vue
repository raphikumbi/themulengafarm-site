<template>
  <div class="flex justify-center">
    <div
        ref="grid"
        class="grid grid-cols-1 sm:grid-cols-2 lg:grid-cols-3 gap-8 max-w-6xl w-full px-4"
    >
      <TeamMemberCard
          v-for="(member, i) in team"
          :key="i"
          :ref="el => cardEls[i] = el"
          v-bind="member"
      />
    </div>
  </div>
</template>

<script setup>
import { onMounted, ref } from "vue";
import gsap from "gsap";
import { ScrollTrigger } from "gsap/ScrollTrigger";
import TeamMemberCard from "./TeamMemberCard.vue";

gsap.registerPlugin(ScrollTrigger);

const grid = ref(null);
const cardEls = ref([]);

const team = [
  {
    src: "/team/portrait-jameson.jpg",
    name: "Jameson",
    func: "Founder, Director",
    loc: "NDOLA, ZAMBIA",
    desc: "I’m passionate about my sustainable farming career, and I love transforming communities, especially supporting less privileged people in society through skills and training. I have a calling in farming, and I look forward to establishing God’s kingdom through farming God’s way. I believe that if we take care of nature, nature will take care of us."
  },
  {
    src: "/team/portrait-lionel.jpg",
    name: "Lionel",
    func: "Founder, Networking",
    loc: "BASEL, SWITZERLAND",
    desc: "I look forward to seeing our culture and society develop into a more human-centered future, where sense, solidarity, communion, and beauty form its core. I love people and traveling, and I enjoy seeing the love of God made practical, starting from the ground up with a shift in agriculture."
  },
  {
    src: "/team/portrait-louis.jpg",
    name: "Louis",
    func: "Media, Architect",
    loc: "STRASBOURG, FRANCE",
    desc: "I’m passionate about my career in media, and I love capturing stories through photography and visual art. I enjoy transforming perspectives and sharing moments that highlight people, culture, and everyday life, especially by giving a voice and visibility to those who are often unseen. I feel called to use media as a tool for a positive impact."
  },

  {
    src: "/team/portrait-sebastian.jpg",
    name: "Sebastian",
    func: "Finances",
    loc: "ZÜRICH, SWITZERLAND",
    desc: "..."
  },
  {
    src: "/team/portrait-raphael.jpg",
    name: "Raphael",
    func: "IT, Media",
    loc: "BASEL, SWITZERLAND",
    desc: "..."
  },
  {
    src: "/team/portrait-francois.jpg",
    name: "François",
    func: "Landscape Architect",
    loc: "BUSCHWILER, FRANCE",
    desc: "..."
  }
];

onMounted(() => {
  const els = cardEls.value
      .filter(Boolean)
      .map(c => c.$el);

  gsap.from(els, {
    opacity: 0,
    y: 40,
    duration: 1.5,
    ease: "power3.out",
    stagger: 0.2,
    scrollTrigger: {
      trigger: grid.value,
      start: "top 75%",
      toggleActions: "play none none none",
      once: false
    }
  });
});
</script>