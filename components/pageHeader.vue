<template>
  <div class="container mx-auto mt-4 lg:px-10 px-3">
    <div class="flex justify-between items-center">
      <div>
        <nuxt-link to="/">
          <img class="lg:w-44 w-28" src="@/static/logo-1.png" alt="" />
        </nuxt-link>
      </div>
      <div v-if="$device.isDesktop" class="lg:flex block">
        <ul class="lg:flex lg:justify-between">
          <li v-for="menuItem in menuItems" :key="menuItem.id">
            <nuxt-link
              class="mr-5 lg:text-lg text-sm font-sans font-medium cursor-pointer"
              :to="menuItem.path"
              >{{ menuItem.titleEn }}</nuxt-link
            >
          </li>
        </ul>
      </div>
      <a-icon
        :style="{ fontSize: '20px', color: '#08c' }"
        v-if="$device.isMobileOrTablet"
        @click="showDrawer"
        type="menu"
      />
      <a-drawer
        v-if="$device.isMobileOrTablet"
        title="Premium cleaning"
        :closable="closable"
        :visible="visible"
        @close="onClose"
      >
        <ul class="lg:flex lg:justify-between">
          <li
            @click="onClose"
            class="mb-5"
            v-for="menuItem in menuItems"
            :key="menuItem.id"
          >
            <nuxt-link
              class="mr-5 text-lg font-sans font-medium cursor-pointer"
              :to="menuItem.path"
              >{{ menuItem.titleEn }}</nuxt-link
            >
          </li>
        </ul>
      </a-drawer>
      <a-back-top v-if="$device.isMobileOrTablet">
        <div class="ant-back-top-inner">
          <div class="contacts">
            <a href="tel:+99364272511">
              <a-button
                class="hover:opacity-70 mr-4"
                size="large"
                type="primary"
                shape="circle"
                icon="phone"
              />
            </a>
            <a href="https://wa.me/+99364272511">
              <img
                class="hover:opacity-70 w-10"
                src="@/assets/img/whatsapp.svg"
                alt=""
              />
            </a>
          </div>
        </div>
      </a-back-top>
      <div
        v-if="$device.isDesktop"
        class="contacts flex items-center justify-center"
      >
        <a href="tel:+99364272511">
          <a-button
            class="hover:opacity-70 mr-4"
            size="large"
            type="primary"
            shape="circle"
            icon="phone"
          />
        </a>
        <a href="https://wa.me/+99364272511">
          <img
            class="hover:opacity-70 w-10"
            src="@/assets/img/whatsapp.svg"
            alt=""
          />
        </a>
      </div>
    </div>
  </div>
</template>
<script>
import menuItems from '@/assets/json/menuItems.json'
export default {
  data() {
    return {
      visible: false,
      closable: true,
    }
  },
  computed: {
    menuItems: () => menuItems,
  },
  methods: {
    showDrawer() {
      this.visible = true
    },
    onClose() {
      this.visible = false
    },
  },
}
</script>
<style scoped>
.nuxt-link-exact-active.nuxt-link-active {
  color: #1890ff;
}
</style>
