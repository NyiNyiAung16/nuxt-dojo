<template>
    <div class="card text-center">
        <img :src="product.image" alt="image thumb" class="thumb">
        <p class="font-bold m-4 text-gray-500 truncate">{{ product.title }}</p>
        <NuxtLink :to="`/products/${product.id}`">
            <p class="btn text-center">View Details</p>
        </NuxtLink>
    </div>
</template>

<script setup>
    const { product }=defineProps(['product'])
</script>

<style scoped>
    .thumb{
        max-width: 70%;
        max-height: 120px;
        margin: 0 auto;
    }
</style>