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
    loc: "NDOLA, ZAMBIA"
  },
  {
    src: "/team/portrait-lionel.jpg",
    name: "Lionel",
    func: "Founder, Networking",
    loc: "BASEL, SWITZERLAND"
  },
  {
    src: "/team/portrait-louis.jpg",
    name: "Louis",
    func: "Media, Architect",
    loc: "STRASBOURG, FRANCE"
  },
  {
    src: "/team/portrait-sebastian.jpg",
    name: "Sebastian",
    func: "Finances",
    loc: "ZÜRICH, SWITZERLAND"
  },
  {
    src: "/team/portrait-raphael.jpg",
    name: "Raphael",
    func: "IT, Media",
    loc: "BASEL, SWITZERLAND"
  },
  {
    src: "/team/portrait-francois.jpg",
    name: "François",
    func: "Landscape Architect",
    loc: "ALSACE, FRANCE"
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