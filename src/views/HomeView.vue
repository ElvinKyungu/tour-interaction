<script setup lang="ts">
import IconBell from '@/components/icons/IconBell.vue'
import IconDown from '@/components/icons/IconDown.vue'
</script>

<template>
  <main class="w-full h-screen flex justify-center items-center">
    <div class="container mx-auto max-w-xl border rounded-lg p-5">
      <div class="flex justify-between items-center">
        <h2 class="flex gap-5 items-center">
          <IconBell/>
          <span>5 New notifications</span>
        </h2>
        <div class="flex justify-center p-2 bg-slate-200 rounded-full cursor-pointer">
          <IconDown/>
        </div>
      </div>
      <ul class="mt-3 space-y-4">
        <li>
          <div class="flex justify-between items-center">
            <h2 class="flex gap-5 items-center">
              <IconBell/>
              <span>5 New notifications</span>
            </h2>
            <div class="flex justify-center p-2 bg-slate-200 rounded-full cursor-pointer">
              <IconDown/>
            </div>
          </div>
        </li>
        <li>
          <div class="flex justify-between items-center">
            <h2 class="flex gap-5 items-center">
              <IconBell/>
              <span>5 New notifications</span>
            </h2>
            <div class="flex justify-center p-2 bg-slate-200 rounded-full cursor-pointer">
              <IconDown/>
            </div>
          </div>
        </li>
        <li>
          <div class="flex justify-between items-center">
            <h2 class="flex gap-5 items-center">
              <IconBell/>
              <span>5 New notifications</span>
            </h2>
            <div class="flex justify-center p-2 bg-slate-200 rounded-full cursor-pointer">
              <IconDown/>
            </div>
          </div>
        </li>
        <li>
          <div class="flex justify-between items-center">
            <h2 class="flex gap-5 items-center">
              <IconBell/>
              <span>5 New notifications</span>
            </h2>
            <div class="flex justify-center p-2 bg-slate-200 rounded-full cursor-pointer">
              <IconDown/>
            </div>
          </div>
        </li>
        <li>
          <div class="flex justify-between items-center">
            <h2 class="flex gap-5 items-center">
              <IconBell/>
              <span>5 New notifications</span>
            </h2>
            <div class="flex justify-center p-2 bg-slate-200 rounded-full cursor-pointer">
              <IconDown/>
            </div>
          </div>
        </li>
      </ul>
    </div>
  </main>
</template>
