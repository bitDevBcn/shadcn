<script setup>
const items = ref([
  {
    title: "Overview",
    path: "/",
    icon:"ri:dashboard-line"
  },
  {
    title: "Transactions",
    path: "/transactions",
    icon:"bitcoin-icons:transactions-filled"
  },
  {
    title: "Account",
    path: "/account",
    icon:"material-symbols-light:manage-accounts-rounded"
  },
  {
    title: "Contacts",
    path: "/contacts",
    icon:"ri:contacts-book-3-line"
  },
  {
    title: "Setting",
    path: "/setting",
    icon:"iconamoon:settings-duotone"
  },
])
</script>
<template>
    <div>
      <header class="flex items-center gap-2 p-4 hover:scale-[101%] transition cursor pointer">
        <Logo />
        <p class="font-bold text-black">Nuxt-Finance</p>
      </header>
      <div class="px-4 grow">
        <div class="grid gap-2">
          <NuxtLink :href="item.path" v-for="(item, index) in items" :key="index" class="flex item-center gap-2 px-2 py-1 rounded cursor-pointer hover:bg-neutral-100">
            <Icon size="20" :name = "item.icon" color="black"/>
            <span>{{ item.title }}</span>  
          </NuxtLink>
        </div>
      </div>
    </div>
  </template>