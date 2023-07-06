<template>
    <div :id="`Product${product.id}`"
        class="bg-white inline-block rounded hover:shadow-[0_0_10px_3px_rgba(0,0,0,0.15)] cursor-pointer">
        <NuxtLink :to="`/item/${product.id}`">
            <img :src="product.url" 
            class="rounded-t 
            2xl:h-[750px] 2xl:w-[600px] 
            xl:h-[750px] xl:w-[600px] 
            lg:h-[750px] lg:w-[600px]
            md:h-[750px] md:w-[600px]
            sm:h-[750px] sm:w-[600px]
            " alt="" >
            <div id="ProductDetails">
                <span class="flex items-center justify-start gap-3 px-1 pt-1">
                    <span class="text-red font-semibold">{{ product.title }}</span>
                    <span class="text-red font-semibold">{{ product.description }}</span>
                    <span class="text-red font-semibold">${{ product.price }}</span>
                </span>
            </div>
        </NuxtLink>
    </div>
</template>

<script setup>
const props = defineProps(['product'])
const { product } = toRefs(props)


</script>