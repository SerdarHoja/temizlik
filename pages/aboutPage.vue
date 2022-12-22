<template>
  <div>
    <a-divider></a-divider>
    <div class="container mx-auto mt-20 mb-20 lg:px-10 px-3">
      <div class="mt-10">
        <h3 class="font-sans font-bold text-4xl mb-2 text-ant-primary">
          {{ about[0].title }}
        </h3>
        <p class="font-sans text-xl">
          {{ about[0].description }}
        </p>
        <aboutComponent class="mt-7" />
        <img class="mt-8 mb-8" src="@/assets/img/11.jpeg" alt="" />
      </div>
    </div>
  </div>
</template>
<script>
import aboutComponent from '../components/aboutComponent.vue'
import about from '@/assets/json/about.json'
export default {
  name: 'IndexPage',
  components: {
    aboutComponent,
  },
  computed: {
    about: () => about,
  },
}
</script>
