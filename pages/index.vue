<script lang="ts" setup>

import { Tabs, TabsContent, TabsList, TabsTrigger } from "@/components/ui/Tabs";

const list = [
  {
    title: "Today",
    component: resolveComponent("TabsToday"),
  },
  {
    title: "Week",
    component: resolveComponent("TabsWeek"),
  },
  {
    title: "Month",
    component: resolveComponent("TabsMonth"),
  },
  {
    title: "Year",
    component: resolveComponent("TabsYear"),
  },
];
</script>

<template>
  <div class="grid w-full h-screen gap-8">
    <header class="flex items-start justify-between">
      <div class="grow">
        <p>Hi, welcome Jordi</p>
        <h1>Dashboard</h1>
      </div>
      <div class="w-[120px] h-[36px] bg-neutral-200"></div>
    </header>
    <main>
      <Tabs default-value="Today" class="w-[400px]">
        <TabsList>
          <TabsTrigger 
          v-for=" item, index in list" :key="index"
          :value="item.title">
            {{ item.title }}
          </TabsTrigger>
        </TabsList>
        <TabsContent 
        v-for="(item, index) in list" :key="index"
        :value="item.title">
        <component :is="item.component" />
        </TabsContent>
      </Tabs>
      <section>Charts</section>
    </main>
    <footer>This is footer</footer>
  </div>
</template>

<style></style>
