<script setup>
import IconEmail from "./icons/IconEmail.vue";
import IconInstagram from "./icons/IconInstagram.vue";
import IconYoutube from "./icons/IconYoutube.vue";
</script>
<template>
  <footer class="w-full  bg-[#161B17] text-gray-200 py-10">
    <div class="max-w-5xl mx-auto px-4 flex flex-col items-center text-center space-y-6">

      <h2 class="text-xl font-semibold">
        The Mulenga Farm
      </h2>

      <div class="flex space-x-6 items-center justify-center">

        <a href="mailto:lionel.kumbartzki@themulengafarm.org"
           class="p-2 rounded-full hover:bg-neutral-800 transition"
           aria-label="Email">
          <IconEmail />
        </a>

        <a href="https://www.instagram.com/themulengafarm/"
           target="_blank"
           class="p-2 rounded-full hover:bg-neutral-800 transition"
           aria-label="Instagram">
          <IconInstagram />
        </a>

        <a href="https://www.youtube.com/@TheMulengaProject-2024"
           target="_blank"
           class="p-2 rounded-full hover:bg-neutral-800 transition"
           aria-label="YouTube">
          <IconYoutube />
        </a>

      </div>

      <p class="text-sm text-neutral-200">
        © 2024 The Mulenga Farm. All Rights Reserved.
      </p>

    </div>
  </footer>
</template>