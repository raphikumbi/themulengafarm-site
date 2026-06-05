<script setup>
import { ref, onMounted } from 'vue'
import gsap from 'gsap'
import { ScrollTrigger } from 'gsap/ScrollTrigger'
import RaiseNowButton from "./buttons/RaiseNowButton.vue"

gsap.registerPlugin(ScrollTrigger);

const contentRef = ref(null);
const bankRef = ref(null);
const grid = ref(null);

onMounted(() => {
  const targets = [contentRef.value, bankRef.value];

  const els = targets
      .filter(Boolean)
      .map(c => c.$el || c);

  if (els.length > 0) {
    gsap.from(els, {
      opacity: 0,
      y: 40,
      duration: 3,
      ease: "power3.out",
      stagger: 0.2,
      scrollTrigger: {
        trigger: grid.value,
        start: "top 75%",
        toggleActions: "play none none none",
        once: false
      }
    });
  }
});
</script>

<template>
  <section ref="grid" class="py-16 md:py-20 overflow-hidden">
    <div class="mx-auto max-w-7xl px-6">

      <div class="max-w-3xl mb-16">
        <h2 class="mb-6 text-4xl font-black tracking-wide text-white md:text-6xl text-center md:text-start">
          Support Us
        </h2>
        <p class="text-lg md:text-xl text-zinc-400 leading-relaxed pt-3 text-center md:text-start">
          We look forward to establishing an economically self-sufficient farm by 2035.
          Until then we need
          <span class="font-bold text-white">
            CHF 3,500 per year
          </span>
          to keep the project growing.
        </p>
      </div>

      <div class="grid gap-5 lg:grid-cols-2 items-stretch overflow-hidden">

        <div ref="contentRef" class="flex flex-col justify-between bg-white/5 p-8 backdrop-blur-md">
          <div>
            <h3 class="mb-4 text-xl font-bold tracking-wider text-white">
              Support us via RaiseNow
            </h3>
            <p class="mb-8 text-sm md:text-base text-zinc-400 leading-relaxed">
              RaiseNow is a digital fundraising platform that helps nonprofits collect donations, manage donor engagement, and process online payments efficiently.
            </p>
          </div>

          <div class="mt-auto flex justify-center md:justify-start">
            <RaiseNowButton />
          </div>
        </div>

        <div ref="bankRef" class="bg-white/5 p-8 backdrop-blur-md">
          <div class="grid gap-8 md:grid-cols-[160px_1fr] md:items-center h-full">

            <div class="flex justify-center">
              <div class="bg-white p-1 transform hover:scale-[1.02] transition-transform duration-300">
                <img src="/qrc-raise-now.png" alt="Donation QR Code" class="h-40 w-40 object-contain select-none"/>
              </div>
            </div>

            <div class="flex flex-col justify-between h-full">
              <div>
                <h3 class="mb-4 text-xl font-bold tracking-wider text-white">
                  Bank Transfer
                </h3>
                <div class="space-y-2 text-sm text-zinc-300">
                  <p>
                    <span class="font-medium text-white">
                      IBAN:
                    </span>
                    CH34 0076 9440 8377 7200 1
                  </p>

                  <p>
                    <span class="font-medium text-white">
                      BANK:
                    </span>
                    BLKBCH22
                  </p>

                  <p>
                    <span class="font-medium text-white">
                      Clearing Nr:
                    </span>
                    769
                  </p>

                  <p>
                    <span class="font-medium text-white">
                      Street:
                    </span>
                    Reinacherstrasse 126
                  </p>

                  <p>
                    <span class="font-medium text-white">
                      City:
                    </span>
                    Basel, CH-4053
                  </p>
                </div>
              </div>
            </div>

          </div>
        </div>

      </div>
    </div>
  </section>
</template>