<script setup>
import SubTitle from "./text/SubTitle.vue";
</script>
<template>
  <section class="w-full max-w-300 mx-auto py-10">
    <div class="grid grid-cols-1 lg:grid-cols-3  items-start">

      <div class="lg:col-span-2 space-y-4">

        <SubTitle title="Our Mission" class="md:pb-5 md:pt-5"/>

        <p class="text-base text-zinc-200 leading-relaxed max-w-3xl text-justify md:text-left ">
          TheMulengaFarm is becoming a commercial farm in Ndola, Zambia, cultivating sustainable agriculture by providing skills training and future employment opportunities for rural communities.<br>
          Our vision is to see that, through our farming activities, orphanages are supported to empower youth and vulnerable people.<br>
          We operate regenerative and sustainable citrus and crop farming, combined with our teaching activities at our Community Training Center in Ndola.<br>
          By doing so, we promote rural agricultural development, improve food security and diversification, and combat climate change by actively working against deforestation.<br>
          Our mission is not only to cultivate crops and trees but also to generate hope, create future perspectives, especially among the youth, and, by doing so, share the love of God. We look forward to seeing the agricultural sector in Zambia change.<br>
        </p>

      </div>

      <div class="space-y-3 flex flex-col justify-center pt-8 max-[1024px]:hidden">
        <div class="overflow-hidden">
          <img
            src="/logo-500.png"
            alt=""
            class="w-full h-auto max-w-82.75 mx-auto"
          />

        </div>

        <h3 class="text-sm font-bold uppercase tracking-widest text-[#A88058]  text-center">
          THE MULENGA PROJECT<br>
          FARMING GOD'S WAY
        </h3>
      </div>

    </div>

    <div class="text-base text-zinc-200 leading-relaxed max-w-7xl text-justify md:text-left">
      <b>TheMulengaFarm (NGO)</b> is a Zambia-based NGO operating farming activities (tree nursery and fields) and teaching programs at our Community Training Center in the neighborhoods of Ndola.<br>
      <b>TheMulengaFarm (ORG)</b> is a Swiss-based registered NGO that funds and supports the work of TheMulengaFarm in Ndola, Zambia.

    </div>
  </section>
</template>