<template>
    <div :id="`Product${product.id}`"
        class="bg-white inline-block rounded hover:shadow-[0_0_10px_3px_rgba(0,0,0,0.15)] cursor-pointer">
        <NuxtLink :to="`/item/${product.id}`">
            <img :src="product.url" class="rounded-t" alt="">
            <div id="ProductDetails">
                <span class="flex items-center justify-start gap-3 px-1 pt-1">
                    <span class="text-black font-semibold">{{ product.title }}</span>
                    <span class="text-black font-semibold">{{ product.description }}</span>
                    <span class="text-black font-semibold">${{ product.price }}</span>
                </span>
            </div>
        </NuxtLink>
    </div>
</template>

<script setup>
const props = defineProps(['product'])
const { product } = toRefs(props)


</script>