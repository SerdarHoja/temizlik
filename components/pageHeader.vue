<template>
  <div class="container mx-auto mt-4 lg:px-10 px-5">
    <div class="flex justify-between items-center">
      <div>
        <nuxt-link to="/">
          <img class="lg:w-24 w-16" src="@/static/logo.png" alt="" />
        </nuxt-link>
      </div>
      <div v-if="$device.isDesktop" class="lg:flex block">
        <ul class="lg:flex lg:justify-between">
          <li v-for="menuItem in menuItems" :key="menuItem.id">
            <nuxt-link
              class="mr-5 lg:text-lg text-sm font-medium cursor-pointer"
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
        title="Günlük temizleme"
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
              class="mr-5 text-lg font-medium cursor-pointer"
              :to="menuItem.path"
              >{{ menuItem.titleEn }}</nuxt-link
            >
          </li>
        </ul>
      </a-drawer>

      <div
        v-if="$device.isDesktop"
        class="contacts flex items-center justify-center"
      >
        <a :href="'tel:' + contacts.phone1">
          <a-button
            class="hover:opacity-70 mr-4"
            size="large"
            type="primary"
            shape="circle"
            icon="phone"
          />
        </a>
        <a :href="'https://wa.me/' + contacts.phone1">
          <img
            class="hover:opacity-70 w-10"
            src="@/assets/img/whatsapp.svg"
            alt=""
          />
        </a>
      </div>
    </div>
    <div class="flex" v-if="$device.isMobileOrTablet">
      <a-back-top class="mr-10 left-5">
        <div class="ant-back-top-inner">
          <a :href="'tel:' + contacts.phone1">
            <a-button
              class="hover:opacity-70 mr-4 w-14 h-14"
              type="primary"
              shape="circle"
            >
              <a-icon :style="{ fontSize: '27px' }" type="phone" />
            </a-button>
          </a>
        </div>
      </a-back-top>
      <a-back-top class="right-9">
        <div class="ant-back-top-inner w-14 h-14">
          <a :href="'https://wa.me/' + contacts.phone1">
            <img
              class="hover:opacity-70"
              src="@/assets/img/whatsapp.svg"
              alt=""
            />
          </a>
        </div>
      </a-back-top>
    </div>
  </div>
</template>
<script>
import menuItems from '@/assets/json/menuItems.json'
import contacts from '@/assets/json/contacts.json'
export default {
  data() {
    return {
      visible: false,
      closable: true,
    }
  },
  computed: {
    menuItems: () => menuItems,
    contacts: () => contacts,
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
