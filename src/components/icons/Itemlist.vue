<script setup>
import {computed} from 'vue'
const products = [
  {
    name: 'Burger',
    price: 20
  },
  {
    name: 'Soda',
    price: 25
  },
  {
    name: 'Water',
    price: 20
  }
]

const totalPrice = computed(() => {
  return products.reduce((sum, item) => item.price + sum, 0)
})
</script>

<template>
  <div>
    <h1>All Products Buyed</h1>
    <ul>
      <li v-for="(item, index) in products" :key="index">{{ item.name }} - P {{ item.price }}</li>
    </ul>
    <p>Total Price: {{ totalPrice }}</p>
  </div>
</template>