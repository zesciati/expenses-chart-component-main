<script setup lang="ts">
import datas from "../data.json";
import { computed, onMounted, ref } from "vue";

interface SpendingItem {
  day: string;
  amount: number;
}
const data: SpendingItem[] = datas;

const isHoveredShowIndex = ref<number | null>(null);
const isLoaded = ref(false);

const maxAmount = computed(() => Math.max(...data.map((d) => d.amount)));
// const totalAmount  = computed(() => data.reduce((sum,item) => sum + item.amount, 0))

onMounted(() => {
  requestAnimationFrame(() => {
    requestAnimationFrame(() => {
      requestAnimationFrame(() => {
        isLoaded.value = true;
      });
    });
  });
});
</script>

<template>
  <main
    class="flex justify-center items-center h-screen flex-col bg-red-100 px-5 space-y-4"
  >
    <section
      class="flex justify-between bg-red-500 w-full p-5 rounded-md sm:w-120 sm:max-w-120"
    >
      <div class="text-white">
        <p class="text-lg">My balance</p>
        <p class="text-3xl font-bold">$921.48</p>
      </div>
      <img src="/images/logo.svg" alt="" />
    </section>

    <section
      class="w-full p-5 rounded-md bg-white space-y-7 sm:w-120 max-w-120"
    >
      <h2 class="text-2xl font-semibold">Spending - Last 7 days</h2>
      <!-- <article class="flex gap-2 flex-wrap pt-10 sm:gap-4 mx-0.5 sm:mx-1" >
        <div class="space-y-2" v-for="item in data" :key="item.day">
          <div class="bg-red-500 h-30 w-10 rounded-sm sm:w-12 2xs:w-8" :style="{height: item.amount + 'px'}"></div>
          <p class="text-center text-brown-400">{{ item.day }}</p>
        </div>
      </article> -->

      <article class="flex items-end justify-between gap-1 h-70 pt-10 sm:gap-3">
        <div
          class="flex flex-col items-center flex-1 h-full justify-end space-y-2"
          v-for="(item, index) in data"
          :key="item.day"
        >
          <div
            @mouseenter="isHoveredShowIndex = index"
            @mouseleave="isHoveredShowIndex = null"
            class="w-full rounded-sm hover:opacity-75 relative transition-[height,opacity] duration-500 ease-out"
            :class="item.amount === maxAmount ? 'bg-cyan-400' : 'bg-red-500'"
            :style="{
              height: isLoaded ? (item.amount / maxAmount) * 100 + '%' : '0%',
              transitionDelay: `${index * 150}ms`,
            }"
          >
            <label
              for=""
              class="bg-brown-950 text-red-100 p-0.5 rounded-md text-xs sm:text-base absolute -top-10"
              v-if="isHoveredShowIndex === index"
              >${{ item.amount }}</label
            >
          </div>
          <p class="text-center text-brown-400 text-sm capitalize">
            {{ item.day }}
          </p>
        </div>
      </article>
      <div class="border border-red-100"></div>

      <article class="flex justify-between items-center">
        <div>
          <p class="text-lg text-brown-400">Total this month</p>
          <h2 class="text-4xl font-semibold">$478.33</h2>
        </div>

        <div class="text-right">
          <p class="font-semibold text-lg">+2.4%</p>
          <p class="text-lg text-brown-400">from last month</p>
        </div>
      </article>
    </section>
  </main>
</template>

<style scoped></style>
