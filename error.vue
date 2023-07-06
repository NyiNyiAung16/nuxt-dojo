<template>
    <div class="card max-w-sm mx-auto p-6 mt-9">
        <p class="mt-7 text-7xl font-bold text-center">{{ error.statusCode }}</p>
        <p class="mt-7 text-6xl text-center">Ooops.</p>
        <p class="mt-7 text-center">{{ error.message }}</p>
        <p class="btn text-center error" @click="handleClearError">Go Home...</p>
    </div>
</template>

<script setup>
    defineProps(['error'])

    const handleClearError=()=>clearError({redirect:'/'})
</script>

<style scoped>
    .error{
        max-width: 100px;
        margin: 20px auto;
        cursor: pointer;
    }
</style>