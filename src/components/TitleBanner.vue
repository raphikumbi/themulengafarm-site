<script setup>
import { computed, ref, onMounted } from 'vue'
import { gsap } from 'gsap'

const emit = defineEmits(['scrollToSection'])

const props = defineProps({
  imageSrc: {
    type: String,
    required: true
  },
  title: {
    type: String,
    default: ''
  },
  overlayOpacity: {
    type: [Number, String],
    default: 40
  }
})

const overlayStyle = computed(() => {
  return { opacity: Number(props.overlayOpacity) / 100 }
})

const words = computed(() => {
  return props.title ? props.title.split(' ') : []
})

const titleRef = ref(null)

// 1. Initial Intro Animation (Pop in)
onMounted(() => {
  if (words.value.length === 0) return

  gsap.fromTo(titleRef.value.querySelectorAll('.animated-word'),
      { opacity: 0, y: 30, scale: 0.8 },
      {
        opacity: 1,
        y: 0,
        scale: 1,
        duration: 0.6,
        ease: 'back.out(1.7)',
        stagger: 0.15
      }
  )
})

// 2. Mouse Tracking Interaction (Magnetic effect)
const onMouseMove = (event) => {
  const el = event.currentTarget
  const rect = el.getBoundingClientRect()

  // Find the center coordinates of the current word
  const centerX = rect.left + rect.width / 2
  const centerY = rect.top + rect.height / 2

  // Calculate distance from mouse to center
  const distanceX = event.clientX - centerX
  const distanceY = event.clientY - centerY

  // Animate the word slightly toward the mouse coordinates
  gsap.to(el, {
    x: distanceX * 0.1, // Move up to 10% closer to the mouse X
    y: distanceY * 0.1, // Move up to 10% closer to the mouse Y
    scale: 1.05,         // Make it slightly bigger on hover
    duration: 0.2,
    ease: 'power2.out',
    overwrite: 'auto'
  })
}

// 3. Reset when mouse leaves the word
const onMouseLeave = (event) => {
  gsap.to(event.currentTarget, {
    x: 0,
    y: 0,
    scale: 1,
    duration: 0.7,
    ease: 'elastic.out(1, 0.5)', // Adds a subtle snappy snap-back effect
    overwrite: 'auto'
  })
}

const handleClick = () => {
  emit('scrollToSection')
}
</script>

<template>
  <div class="relative w-screen h-screen overflow-hidden bg-black">

    <img
        :src="imageSrc"
        :alt="title"
        class="absolute inset-0 w-full h-full object-cover select-none"
    />

    <div
        class="absolute inset-0 bg-black transition-opacity duration-300"
        :style="overlayStyle"
    ></div>

    <div class="relative z-10 flex items-center justify-center w-full h-full px-4">
      <h1
          ref="titleRef"
          @click="handleClick"
          class="flex flex-wrap justify-center gap-x-6 gap-y-2 text-5xl md:text-8xl lg:text-8xl font-black text-white text-center uppercase tracking-wider max-w-5xl drop-shadow-sm"
      >
        <span
            v-for="(word, index) in words"
            :key="index"
            @mousemove="onMouseMove"
            @mouseleave="onMouseLeave"
            class="animated-word inline-block will-change-transform cursor-pointer select-none py-2 px-1 tracking-wider"
        >
          {{ word }}
        </span>
      </h1>
    </div>

  </div>
</template>