<script setup>
import { inject } from 'vue'
import CartItem from './CartItem.vue'

const { cart, removeForCart } = inject('cart')
</script>

<template>
  <div class="flex flex-col gap-5" v-auto-animate>
    <CartItem
      v-for="item in cart"
      :key="item.id"
      :title="item.title"
      :price="item.price"
      :image-url="item.imageUrl"
      @on-click-remove="() => removeForCart(item)"
    />
  </div>
</template>
