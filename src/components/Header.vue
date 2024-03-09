<script setup lang="ts">
import { RouterLink } from 'vue-router'
</script>

<template>
  <div class="fixed top-0 z-30 w-full bg-white">
    <div class="mx-auto max-w-screen-xl px-4 lg:px-8 sm:px-6">
      <div class="h-16 flex items-center justify-between">
        <div class="md:flex md:items-center md:gap-12">
          <RouterLink
            to="/"
            class="block text-teal-600"
          >
            宁波美食文化
          </RouterLink>
        </div>

        <div class="md:block">
          <nav aria-label="Global">
            <ul class="flex items-center gap-6 text-sm">
              <li>
                <RouterLink
                  to="/foods"
                  class="text-gray-500 transition hover:text-gray-500/75"
                >
                  美食
                </RouterLink>
              </li>

              <li>
                <RouterLink
                  to="/history"
                  class="text-gray-500 transition hover:text-gray-500/75"
                >
                  历史文化
                </RouterLink>
              </li>

              <li>
                <RouterLink
                  to="/restaurants"
                  class="text-gray-500 transition hover:text-gray-500/75"
                >
                  餐厅
                </RouterLink>
              </li>
            </ul>
          </nav>
        </div>
      </div>
    </div>
  </div>
</template>
