<script setup lang="ts">
import { ref } from 'vue'
import { restaurants } from '~/constants/restaurants'

const commentModal = ref(false)

function openCommentModal() {
  commentModal.value = true
}

function closeCommentModal() {
  commentModal.value = false
}
</script>

<template>
  <section>
    <!-- 添加评论模态框 -->
    <div v-if="commentModal" class="fixed inset-0 bg-gray-500 bg-opacity-75 transition-opacity" aria-hidden="ture" />
    <div class="mx-auto max-w-screen-2xl px-4 py-12 lg:px-8 lg:py-16 sm:px-6">
      <div class="grid grid-cols-1 mt-8 gap-4 md:grid-cols-3">
        <blockquote v-for="restaurant in restaurants" :key="restaurant.title" class="h-full flex flex-col justify-between bg-white p-6 shadow-lg sm:p-8">
          <img :alt="restaurant.title" :src="restaurant.imgUrl" class="h-56 w-full rounded-md object-cover">

          <div class="mt-2">
            <dl>
              <p class="text-5 text-gray-800 font-bold">
                {{ restaurant.title }}
              </p>

              <a
                class="mt-3 inline-block border border-indigo-600 rounded px-5 py-2 text-sm text-indigo-600 font-medium active:bg-indigo-500 hover:bg-indigo-600 hover:text-white focus:outline-none focus:ring"
                @click.prevent="openCommentModal"
              >
                评论
              </a>
            </dl>
          </div>
        </blockquote>
      </div>
    </div>
    <!-- 评论模态框内容 -->
    <div v-if="commentModal" class="fixed inset-0 flex items-center justify-center p-4">
      <div class="max-w-2xl w-full rounded-lg bg-white p-6 shadow-xl">
        <div class="flex items-center justify-between border-b pb-3">
          <h3 class="text-lg font-semibold">
            评论
          </h3>
          <button @click="closeCommentModal">
            <span class="text-xl">&times;</span>
          </button>
        </div>
        <div class="mt-4">
          <textarea class="h-40 w-full border rounded p-2" placeholder="请输入您的评论..." />
        </div>
        <div class="mt-4 flex justify-end">
          <button
            class="rounded bg-indigo-600 px-5 py-2 text-white hover:bg-indigo-500"
            @click="closeCommentModal"
          >
            提交
          </button>
        </div>
      </div>
    </div>
  </section>
</template>

<route lang="yaml">
  meta:
    layout: home
</route>
