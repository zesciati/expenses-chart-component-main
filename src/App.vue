<script setup lang="ts"></script>

<template>
  <main
    class="flex justify-center items-center h-screen flex-col bg-red-100 px-5 space-y-4 "
  >
    <section class="flex justify-between bg-red-500 w-full p-5 rounded-md sm:w-120 sm:max-w-120">
      <div class="text-white">
        <p class="text-lg">My balance</p>
        <p class="text-3xl font-bold">$921.48</p>
      </div>
      <img src="/images/logo.svg" alt="" />
    </section>

    <section class="w-full p-5 rounded-md bg-white space-y-7 sm:w-120 max-w-120">
      <h2 class="text-2xl font-semibold">Spending - Last 7 days</h2>
      <article class="flex gap-2 flex-wrap pt-10 sm:gap-4 mx-auto">
        <div class="space-y-2">
          <div class="bg-red-500 h-30 w-10 rounded-sm sm:w-12"></div>
          <p class="text-center text-brown-400">mon</p>
        </div>

        <div class="space-y-2">
          <div class="bg-red-500 h-30 w-10 rounded-sm sm:w-12"></div>
          <p class="text-center text-brown-400">tue</p>
        </div>
        <div class="space-y-2">
          <div class="bg-red-500 h-30 w-10 rounded-sm sm:w-12"></div>
          <p class="text-center text-brown-400">wed</p>
        </div>
        <div class="space-y-2">
          <div class="bg-red-500 h-30 w-10 rounded-sm sm:w-12"></div>
          <p class="text-center text-brown-400 ">thu</p>
        </div>

        <div class="space-y-2">
          <div class="bg-red-500 h-30 w-10 rounded-sm sm:w-12"></div>
          <p class="text-center text-brown-400">fri</p>
        </div>

        <div class="space-y-2">
          <div class="bg-red-500 h-30 w-10 rounded-sm sm:w-12"></div>
          <p class="text-center text-brown-400">sat</p>
        </div>

        <div class="space-y-2">
          <div class="bg-red-500 h-30 w-10 rounded-sm sm:w-12"></div>
          <p class="text-center text-brown-400">sun</p>
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

