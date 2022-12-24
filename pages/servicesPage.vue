<template>
  <div>
    <a-divider></a-divider>
    <div class="container mx-auto mt-20 mb-20 lg:px-10 px-5">
      <div class="mt-10">
        <h3 class="font-bold text-4xl mb-2 text-ant-primary">
          {{ services.title }}
        </h3>
        <p class="text-xl">
          {{ services.description }}
        </p>
        <chooseComponent class="mt-7" />
        <a-divider></a-divider>
        <serviceComponent class="mt-7" />
      </div>
    </div>
  </div>
</template>
<script>
import serviceComponent from '../components/serviceComponent.vue'
import chooseComponent from '../components/chooseComponent.vue'
import services from '@/assets/json/services.json'

export default {
  name: 'IndexPage',
  components: {
    serviceComponent,
    chooseComponent,
  },
  computed: {
    services: () => services,
  },
}
</script>
