<template>
  <div>
    <p class="font-sans font-bold text-2xl mb-2 text-my-gray">
      {{ services.title }}
    </p>
    <div class="flex justify-between">
      <hooper :settings="hooperSettings" style="height: auto">
        <slide
          class="flex justify-center"
          v-for="service in services.articles"
          :key="service.id"
        >
          <a-card hoverable style="width: 300px">
            <template #cover>
              <img :src="service.img" :alt="service.name" />
            </template>
            <a-card-meta :title="service.name">
              <template #description>
                {{ service.description }}
              </template>
            </a-card-meta>
          </a-card>
        </slide>
        <hooper-navigation slot="hooper-addons"></hooper-navigation>
      </hooper>
    </div>
  </div>
</template>
<script>
import { Hooper, Slide, Navigation as HooperNavigation } from 'hooper'
import 'hooper/dist/hooper.css'
import services from '@/assets/json/services.json'
export default {
  data() {
    return {
      hooperSettings: {
        infiniteScroll: true,
        breakpoints: {
          320: {
            itemsToShow: 1,
          },
          500: {
            itemsToShow: 2,
          },
          1000: {
            itemsToShow: 4,
          },
        },
      },
    }
  },
  computed: {
    services: () => services,
  },
  components: {
    Hooper,
    Slide,
    HooperNavigation,
  },
}
</script>
