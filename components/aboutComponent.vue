<template>
  <div class="lg:flex justify-between block">
    <p class="lg:w-1/2 w-full text-base font-light">
      {{ about[0].content1 }}
    </p>
    <p class="lg:w-1/2 w-full text-base font-light">
      {{ about[0].content2 }}
    </p>
  </div>
</template>
<script>
import about from '@/assets/json/about.json'
export default {
  computed: {
    about: () => about,
  },
}
</script>
