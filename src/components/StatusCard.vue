<script setup>
import StatusIcon from './StatusIcon.vue';

const statusProps = defineProps(["data"])

const onStatusClassChanged = (status) => {
  return status === 'Online'
    ? 'bg-green-100 text-green-800 text-xs font-medium me-2 px-2.5 py-0.5 rounded-full dark:bg-green-900 dark:text-green-300'
    : 'bg-red-100 text-red-800 text-xs font-medium me-2 px-2.5 py-0.5 rounded-full dark:bg-red-900 dark:text-red-300';
};



</script>
<template>
  <div class="rounded-lg overflow-hidden shadhow-lg hover:bg-[#090c10]">
    <div class="flex flex-row justify-between items-center">
      <div class=" px-6 max-w-screen-xl py-4 text-gray-900 dark:text-gray-300">
        <div class="flex flex-row items-center">
          <span :class="onStatusClassChanged(statusProps.data.status)">
            {{ statusProps.data.status }}
          </span>
          <div class="font-bold text-xl mb-2">
            {{ statusProps.data.statusTitle }}
          </div>
        </div>
        <p class="text-sm ml-16 text-[#666] whitespace-normal overflow-ellipsis max-w-4xl">
          {{ statusProps.data.statusText }}
        </p>
      </div>

      <div class="flex flex-col">
        <div class="flex flex-wrap">
          <div v-for="index in 30" :key="index">
            <StatusIcon :title="'2024-06-07'" />
          </div>
        </div>
        <div class="flex justify-between align-items-center word text-[#aaa] text-sm">
          <div>43m ago</div><!---->
          <div>now</div>
        </div>
      </div>

    </div>
  </div>
</template>

<style scoped>
.beat {
  background-color: #5cdd8b;
  border-radius: 50rem;
}
</style>