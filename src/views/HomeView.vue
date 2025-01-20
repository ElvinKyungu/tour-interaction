<script setup lang="ts">
import { ref, nextTick } from 'vue'
import { animate } from 'motion'
import IconBell from '@/components/icons/IconBell.vue'
import IconDown from '@/components/icons/IconDown.vue'
import IconBadge from "@/components/icons/IconBadge.vue"
import IconCheckCircle from '@/components/icons/IconCheckCircle.vue'
import IconMessage from '@/components/icons/IconMessage.vue'
import IconTag from '@/components/icons/IconTag.vue'
import IconClock from '@/components/icons/IconClock.vue'
const containerRef = ref<HTMLElement | null>(null)
const isOpen = ref(false)
const messages = [
  {
    id: 1,
    icon: IconMessage,
    title: "New message",
    description: "Sara sent you a message.",
    textLeft: 'Just Now'
  },
  {
    id: 2,
    icon: IconBadge,
    title: "Level Up",
    description: "You've unlocked a new achievement.",
    textLeft: '2 min ago'
  },
  {
    id: 3,
    icon: IconClock,
    title: "Reminder: Meeting today",
    description: "Your team meeting start  in 30 minutes.",
    textLeft: '3 hours ago'
  },
  {
    id:4,
    icon: IconTag,
    title: "Special Offer!",
    description: "Save 20% off on subscription upgrade.",
    textLeft: '12 hours ago'
  },
  {
    id: 5,
    icon: IconCheckCircle,
    title: "Task Assigned!",
    description: "A new task is waiting your action.",
    textLeft: 'Yesterday'
  }
]
const openContainer = async () => {
  isOpen.value = !isOpen.value
  if (containerRef.value) {
    await nextTick()

    if (isOpen.value) {
      animate(
        containerRef.value,
        { height: '400px', type: 'spring' },
        { duration: 0.3, easing: 'ease-in-out' }
      )
    } else {
      animate(
        containerRef.value,
        { height: '88px', type: 'spring'},
        { duration: 0.4, easing: 'ease-in-out' }
      )
    }
  }
}
</script>

<template>
  <main class="w-full h-screen flex justify-center items-center">
    <div ref="containerRef" class="container mx-auto max-w-xl border rounded-lg p-5">
      <div class="flex justify-between items-center cursor-pointer" @click="openContainer">
        <div class="flex gap-5 items-center">
          <div class="p-3 rounded-lg bg-slate-200">
            <IconBell :class="{'w-6 h-6': !isOpen, 'w-4 h-4': isOpen}" />
          </div>
          <div class="flex flex-col">
            <span :class="{'text-lg font-medium': !isOpen, 'text-base font-medium': isOpen}">5 New notifications</span>
            <span class="transition-all text-gray-500" :class="{'hidden transition-all': isOpen}">What happening arround you ?</span>
          </div>
        </div>
        <div class="flex p-2 justify-center bg-slate-100 rounded-full">
          <IconDown :class="{'w-5 h-5': !isOpen, 'w-4 h-4 rotate-180': isOpen}"/>
        </div>
      </div>
      <ul
        class="overflow-hidden transition-all mt-5 space-y-4"
        :class="{'opacity-0': !isOpen, 'opacity-100': isOpen}"
        :style="{ height: isOpen ? 'auto' : '0px', opacity: isOpen ? '1' : '0' }"
      >
        <li v-for="message in messages" :key="message.id">
          <div class="flex justify-between items-center">
            <div class="flex gap-5 items-center">
              <div class="p-3 rounded-lg bg-slate-100">
                <component :is="message.icon" :class="{'w-6 h-6': !isOpen, 'w-4 h-4 rotate-180': isOpen}" />
              </div>
              <div class="flex flex-col">
                <span class="text-base">{{ message.title }}</span>
                <span class="text-sm text-gray-600">{{ message.description }}</span>
              </div>
            </div>
            <div class="flex justify-center">
              <span class="text-gray-500 text-sm">{{ message.textLeft }}</span>
            </div>
          </div>
        </li>
      </ul>
    </div>
  </main>
</template>
