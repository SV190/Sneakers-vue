<script setup>
const emit = defineEmits(['OnClickRemove'])

defineProps({
  id: Number,
  title: String,
  imageUrl: String,
  price: Number
})
</script>

<template>
  <div class="flex border border-slate-200 p-4 rounded-xl gap-4">
    <img :src="imageUrl" class="w-16 h-16" alt="title" />
    <div class="flex flex-col flex-1">
      <p>{{ title }}</p>
      <div class="flex justify-between mt-2">
        <b class="flex-1">{{ price }} руб.</b>
        <img
          @click="emit('OnClickRemove')"
          class="opacity-40 hover:opacity-100 cursor-poiner transition"
          src="/close.svg"
          alt="Close"
        />
      </div>
    </div>
  </div>
</template>
