<template>
  <div>
    <pageHeader />
    <Nuxt />
    <pageFooter />
  </div>
</template>
<script>
import pageHeader from '../components/pageHeader.vue'

import pageFooter from '../components/pageFooter.vue'
export default {
  name: 'IndexPage',
  components: {
    pageHeader,
    pageFooter,
  },
}
</script>
