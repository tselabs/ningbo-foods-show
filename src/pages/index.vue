<script setup>
import { RouterLink } from 'vue-router'
import { foods } from '~/constants/foods'

import { restaurants } from '~/constants/restaurants'
</script>

<template>
  <div class="mx-auto px-4 py-8 container">
    <!-- 首页标题 -->

    <!-- 传统美食栏目 -->
    <section>
      <div class="mx-auto max-w-screen-2xl px-4 py-12 lg:px-8 lg:py-16 sm:px-6">
        <div class="md:flex md:items-center md:justify-between">
          <div class="max-w-250">
            <h2 class="text-4xl text-gray-900 font-bold tracking-tight sm:text-5xl">
              宁波传统美食与特色菜
            </h2>

            <p class="mt-6 text-gray-700 leading-relaxed">
              宁波菜简称“甬菜”，采用原料以海鲜居多，鲜咸合一，它是浙菜系列中最具特色的一个地方菜。基于“鱼米之乡”、“文化之邦”，既受赐于大自然得天独厚的地理条件，更得力于历代厨师矢志不渝的烹饪实践，渐成风格，自成一家。
            </p>
          </div>

          <RouterLink
            to="/foods"
            class="hover: mt-6 inline-flex shrink-0 items-center gap-2 border border-rose-600 rounded-full px-5 py-3 text-rose-600 transition md:mt-0 hover:bg-rose-600 hover:text-white"
          >
            <span class="font-medium"> 了解更多美食 </span>

            <svg
              xmlns="http://www.w3.org/2000/svg"
              class="size-4 rtl:rotate-180"
              fill="none"
              viewBox="0 0 24 24"
              stroke="currentColor"
            >
              <path
                stroke-linecap="round"
                stroke-linejoin="round"
                stroke-width="2"
                d="M14 5l7 7m0 0l-7 7m7-7H3"
              />
            </svg>
          </RouterLink>
        </div>

        <div class="grid grid-cols-1 mt-8 gap-4 md:grid-cols-3">
          <!-- 循环foods数组的前3个元素 -->
          <blockquote v-for="food in foods.slice(0, 3)" :key="food.title" class="h-full flex flex-col justify-between bg-white p-6 shadow-lg sm:p-8">
            <img :alt="food.title" :src="food.imgUrl" class="h-56 w-full rounded-md object-cover">

            <div class="mt-2">
              <dl>
                <p class="text-2xl text-rose-600 font-bold sm:text-3xl">
                  {{ food.title }}
                </p>

                <p class="mt-4 text-gray-700 leading-relaxed">
                  {{ food.desc }}
                </p>
              </dl>
            </div>
          </blockquote>
        </div>
      </div>
    </section>

    <section>
      <div class="mx-auto max-w-screen-2xl px-4 py-12 lg:px-8 lg:py-16 sm:px-6">
        <div class="md:flex md:items-center md:justify-between">
          <div class="max-w-xl">
            <h2 class="text-4xl text-gray-900 font-bold tracking-tight sm:text-5xl">
              宁波美食地点与餐厅
            </h2>
          </div>

          <RouterLink
            to="/restaurants"
            class="hover: mt-6 inline-flex shrink-0 items-center gap-2 border border-rose-600 rounded-full px-5 py-3 text-rose-600 transition md:mt-0 hover:bg-rose-600 hover:text-white"
          >
            <span class="font-medium"> 查看更多地点 </span>

            <svg
              xmlns="http://www.w3.org/2000/svg"
              class="size-4 rtl:rotate-180"
              fill="none"
              viewBox="0 0 24 24"
              stroke="currentColor"
            >
              <path
                stroke-linecap="round"
                stroke-linejoin="round"
                stroke-width="2"
                d="M14 5l7 7m0 0l-7 7m7-7H3"
              />
            </svg>
          </RouterLink>
        </div>

        <div class="grid grid-cols-1 mt-8 gap-4 md:grid-cols-3">
          <blockquote v-for="restaurant in restaurants.slice(0, 3)" :key="restaurant.title" class="h-full flex flex-col justify-between bg-white p-6 shadow-lg sm:p-8">
            <img :alt="restaurant.title" :src="restaurant.imgUrl" class="h-56 w-full rounded-md object-cover">

            <div class="mt-2">
              <dl>
                <p class="text-2xl text-rose-600 font-bold sm:text-3xl">
                  {{ restaurant.title }}
                </p>

                <p class="mt-4 text-gray-700 leading-relaxed">
                  {{ restaurant.address }}
                </p>
              </dl>
            </div>
          </blockquote>
        </div>
      </div>
    </section>

    <section>
      <div class="mx-auto max-w-screen-xl px-4 py-8 lg:px-8 lg:py-16 sm:px-6 sm:py-12">
        <div class="grid grid-cols-1 gap-8 lg:grid-cols-2 lg:gap-16">
          <div class="relative h-64 overflow-hidden rounded-lg lg:order-last lg:h-full sm:h-80">
            <img
              alt=""
              src="https://pic2.zhimg.com/v2-bfbdab7b9c74b081ae4099037090bc6d_b.webp"
              class="absolute inset-0 h-full w-full object-cover"
            >
          </div>

          <div class="lg:py-24">
            <h2 class="text-3xl font-bold sm:text-4xl">
              宁波美食文化历史
            </h2>

            <RouterLink
              to="/history"
              class="mt-8 inline-block rounded bg-indigo-600 px-12 py-3 text-sm text-white font-medium transition hover:bg-indigo-700 focus:outline-none focus:ring focus:ring-yellow-400"
            >
              了解更多
            </RouterLink>
          </div>
        </div>
      </div>
    </section>
  </div>
</template>

<route lang="yaml">
  meta:
    layout: home
</route>
