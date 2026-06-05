<script setup>
defineProps(['size']);
</script>

<template>
  <svg
      fill="none"
      stroke="currentColor"
      stroke-width="1.5"
      :width="size || 24"
      :height="size || 24"
      viewBox="0 0 24 24"
  >
    <rect
        x="2"
        y="2"
        width="20"
        height="20"
        rx="5"
        ry="5"
    />

    <path
        stroke-linecap="round"
        stroke-linejoin="round"
        d="M16 11.37A4 4 0 1112.63 8 4 4 0 0116 11.37z"
    />

    <line
        x1="17.5"
        y1="6.5"
        x2="17.51"
        y2="6.5"
        stroke-linecap="round"
        stroke-width="2.5"
    />
  </svg>
</template>