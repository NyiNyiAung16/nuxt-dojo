<template>
    <div class="grid grid-cols-4 gap-5">
      <div v-for="p in products" :key="p.id">
        <ProductCard :product="p"/>
      </div>
    </div>
  </template>
  
  <script setup>
    definePageMeta({
      layout:'products'
    })

    //fetch products data
    const {data:products}=await useFetch('https://fakestoreapi.com/products')

    useHead({
        title:'nuxt dojo | merch',
        meta:[
            {name:"description", content:'nuxt 3 merch'}
        ]
    })
  </script>
  
  <style scoped>
  
  </style>