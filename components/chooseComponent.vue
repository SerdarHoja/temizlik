<template>
  <div>
    <p class="font-bold text-2xl mb-2 !text-my-gray">
      {{ choose.title }}
    </p>
    <div class="flex justify-between">
      <hooper :settings="hooperSettings" style="height: auto">
        <slide
          class="flex justify-center"
          v-for="choise in choose.articles"
          :key="choise.id"
        >
          <a-card class="rounded-3xl" hoverable>
            <template #cover>
              <img
                class="mx-auto w-40 h-40 my-10"
                :src="`/choose/${choise.path}.png`"
                :alt="choise.name"
              />
            </template>
            <a-divider></a-divider>
            <a-card-meta :title="choise.name">
              <template #description>
                {{ choise.description }}
              </template>
            </a-card-meta>
          </a-card>
        </slide>
        <hooper-navigation slot="hooper-addons"></hooper-navigation>
      </hooper>
    </div>
    <a-divider></a-divider>
    <div>
      <p class="font-bold text-2xl mb-2 !text-my-gray">
        {{ steps.title }}
      </p>
      <a-steps :current="current">
        <a-step
          v-for="step in steps.articles"
          :key="step.id"
          :title="step.title"
          :description="step.description"
        />
      </a-steps>
    </div>
  </div>
</template>
<script>
import { Hooper, Slide, Navigation as HooperNavigation } from 'hooper'
import 'hooper/dist/hooper.css'
import choose from '@/assets/json/choose.json'
import steps from '@/assets/json/steps.json'
export default {
  data() {
    return {
      current: 4,
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
  components: {
    Hooper,
    Slide,
    HooperNavigation,
  },
  computed: {
    choose: () => choose,
    steps: () => steps,
  },
}
</script>
