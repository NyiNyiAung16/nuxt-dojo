<template>

    <Head>
      <Title>Nuxt Dojo | {{ product.title }}</Title>
      <Meta name="description" :content="product.description" />
    </Head>

    <div>
      <ProductDetail :product="product"/>
    </div>
  </template>
  
  <script setup>

    definePageMeta({
      layout:'products'
    })

    const { id }=useRoute().params
    const uri='https://fakestoreapi.com/products/' + id

    //fetch the product detail
    const { data:product }=await useFetch(uri, { key: id })

    //error handle
    if(!product.value){
      throw createError({statusCode:404, statusMessage: 'Product not found', fatal:true})
    }

  </script>
  
  <style scoped>
  
  </style>