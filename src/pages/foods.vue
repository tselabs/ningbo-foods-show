<script setup>
import { RouterLink } from 'vue-router'
import { foods } from '~/constants/foods'
</script>

<template>
  <!-- 首页标题 -->

  <!-- 传统美食栏目 -->
  <section>
    <div class="mx-auto max-w-screen-2xl px-4 py-12 lg:px-8 lg:py-16 sm:px-6">
      <div class="grid grid-cols-1 mt-8 gap-4 md:grid-cols-3">
        <blockquote v-for="food in foods" :key="food.title" class="h-full flex flex-col justify-between bg-white p-6 shadow-lg sm:p-8">
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
</template>

<route lang="yaml">
  meta:
    layout: home
</route>
