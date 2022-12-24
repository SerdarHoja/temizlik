<template>
  <div>
    <a-divider></a-divider>
    <mainSlider class="mt-5" />
    <div class="container mx-auto mt-20 mb-20 lg:px-10 px-5">
      <div class="mt-10">
        <h3 class="font-bold lg:text-4xl text-2xl mb-2 text-ant-primary">
          {{ about[0].title }}
        </h3>
        <p class="text-xl">
          {{ about[0].description }}
        </p>
        <aboutComponent class="mt-7" />
      </div>
    </div>
    <div class="bg-image img1">
      <div v-if="$device.isMobileOrTablet">
        <h6
          class="text-center text-ant-primary font-bold text-2xl uppercase pt-8"
        >
          {{ about[0].title }}
        </h6>
        <p class="text-white font-light text-center text-lg mt-5">
          {{ about[0].miniContent }}
        </p>
      </div>
    </div>
    <div class="container mx-auto mt-20 mb-20 lg:px-10 px-5">
      <div class="mt-10">
        <h3 class="font-bold lg:text-4xl text-2xl mb-2 text-ant-primary">
          {{ services.title }}
        </h3>
        <p class="text-xl">
          {{ services.description }}
        </p>
        <serviceComponent class="mt mt-7" />
      </div>
    </div>
    <div class="bg-image img2"></div>
    <div class="container mx-auto mt-20 mb-20 lg:px-10 px-5">
      <div class="mt-10">
        <h3 class="font-bold text-4xl mb-2 text-ant-primary">
          {{ choose.title }}
        </h3>
        <p class="text-xl">
          {{ choose.description }}
        </p>
        <chooseComponent class="mt mt-7" />
      </div>
    </div>
  </div>
</template>

<script>
import mainSlider from '../components/mainSlider.vue'
import aboutComponent from '../components/aboutComponent.vue'
import serviceComponent from '../components/serviceComponent.vue'
import chooseComponent from '../components/chooseComponent.vue'
import about from '@/assets/json/about.json'
import services from '@/assets/json/services.json'
import steps from '@/assets/json/steps.json'
import choose from '@/assets/json/choose.json'
export default {
  name: 'IndexPage',
  components: {
    mainSlider,
    aboutComponent,
    serviceComponent,
    chooseComponent,
  },
  computed: {
    about: () => about,
    services: () => services,
    steps: () => steps,
    choose: () => choose,
  },
}
</script>
