<script setup>
import { onMounted, ref } from 'vue'
import CardList from '../components/CardList.vue'
import axios from 'axios'

const favorites = ref([])

onMounted(async () => {
  try {
    const { data } = await axios.get(
      'https://0729a33675c66ef1.mokky.dev/favorites?_relations=items'
    )

    favorites.value = data.map((obj) => obj.item)
  } catch (err) {
    console.log(err)
  }
})
</script>

<template>
  <h2 class="text-3xl font-bold mb-8">Мои закладки</h2>

  <CardList :items="favorites" is-favorites />
</template>
