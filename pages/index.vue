<template>
  <div>
    <a-divider></a-divider>
    <mainSlider class="mt-5" />
    <div class="container mx-auto mt-20 mb-20 lg:px-10 px-3">
      <div class="mt-10">
        <h3
          class="font-sans font-bold lg:text-4xl text-2xl mb-2 text-ant-primary"
        >
          {{ about[0].title }}
        </h3>
        <p class="font-sans text-xl">
          {{ about[0].description }}
        </p>
        <aboutComponent class="mt-7" />
      </div>
    </div>
    <div class="bg-image img1"></div>
    <div class="container mx-auto mt-20 mb-20 lg:px-10 px-3">
      <div class="mt-10">
        <h3
          class="font-sans font-bold lg:text-4xl text-2xl mb-2 text-ant-primary"
        >
          {{ services.title }}
        </h3>
        <p class="font-sans text-xl">
          {{ services.description }}
        </p>
        <serviceComponent class="mt mt-7" />
      </div>
    </div>
    <div class="bg-image img2"></div>
    <div class="container mx-auto mt-20 mb-20 lg:px-10 px-3">
      <div class="mt-10">
        <h3 class="font-sans font-bold text-4xl mb-2 text-ant-primary">
          {{ choose.title }}
        </h3>
        <p class="font-sans text-xl">
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
