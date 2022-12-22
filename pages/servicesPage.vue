<template>
  <div>
    <a-divider></a-divider>
    <div class="container mx-auto mt-20 mb-20 lg:px-10 px-3">
      <div class="mt-10">
        <h3 class="font-sans font-bold text-4xl mb-2 text-ant-primary">
          Services
        </h3>
        <p class="font-sans text-xl">
          Premium Temizlik Hizmetleri olarak İstanbul da 10 Yılı Aşkın bir
          süredir Hizmet sunmaktayız.
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

export default {
  name: 'IndexPage',
  components: {
    serviceComponent,
    chooseComponent,
  },
}
</script>
