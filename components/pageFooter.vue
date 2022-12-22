<template>
  <div>
    <a-divider></a-divider>
    <div class="container mx-auto mt-4 lg:px-10 px-3">
      <div class="flex justify-between items-center">
        <div>
          <nuxt-link to="/">
            <img class="w-44" src="@/static/logo-1.png" alt="" />
          </nuxt-link>
        </div>

        <div class="contacts flex items-center justify-center">
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
      <div class="mt-8 lg:flex justify-between">
        <div class="lg:w-1/4">
          <div class="address">
            <p class="text text-base font-light mb-5 text-my-gray">
              {{ contacts.address }}
            </p>
            <p class="text text-base font-light mb-5 text-my-gray">
              Phone:{{ contacts.phone1 }}
            </p>
            <p class="text text-base font-light mb-5 text-my-gray">
              E-mail:{{ contacts.mail1 }}
            </p>
          </div>
        </div>
        <div class="lg:w-1/4 lg:flex hidden justify-end">
          <ul class="flex justify-around flex-col">
            <li v-for="menuItem in menuItems" :key="menuItem.id">
              <nuxt-link
                class="mr-5 lg:text-lg text-sm font-sans font-medium cursor-pointer"
                :to="menuItem.path"
                >{{ menuItem.titleEn }}</nuxt-link
              >
            </li>
          </ul>
        </div>
      </div>
      <a-divider></a-divider>
      <div class="flex justify-center">
        <p class="text-lg text-my-gray">&#9400;</p>
        <p class="text-lg text-my-gray">All rights reserved</p>
      </div>
    </div>
  </div>
</template>
<script>
import menuItems from '@/assets/json/menuItems.json'
import contacts from '@/assets/json/contacts.json'
export default {
  computed: {
    menuItems: () => menuItems,
    contacts: () => contacts,
  },
}
</script>
<style scoped>
.nuxt-link-exact-active.nuxt-link-active {
  color: #1890ff;
}
</style>
