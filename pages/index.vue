<template>
    <MainLayout />
    <div id="homeBody" class="mt-10">
        <div class="flex">
            <div class="mx-auto text-3xl block relative">
                <div class="font-semibold">Main Watches</div>
                <hr class="mt-5 w-40 mx-auto h-1 my-8 bg-gray-200 border-0 rounded dark:bg-gray-400">
            </div>
        </div>

        <div class="flex">
            <div class="text-xl italic relative mx-auto justify-between items-center">
                Some of the most requested mods:
            </div>
        </div>

        <div class="grid xl:grid-cols-3 lg:grid-cols-3 md:grid-cols-1 sm:grid-cols-1 grid-cols-1 gap-4 flex mt-10">
            <div v-if="products" v-for="product in products" :key="product" class="flex">
                <Product :product="product" class="mx-auto max-w-[500px] max-h-[750px] flex" />
            </div>
        </div>
    </div>
</template>

<script setup>
import MainLayout from '@/layouts/MainLayout.vue'

const products = [
    { id: 1, title: "Title 1", description: "Desc blabla", url: "https://images.unsplash.com/photo-1524805444758-089113d48a6d?ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D&auto=format&fit=crop&w=688&q=80", price: 888 },
    { id: 2, title: "Title 2", description: "Desc blabla", url: "https://images.unsplash.com/photo-1517463700628-5103184eac47?ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxzZWFyY2h8MTd8fHdhdGNofGVufDB8fDB8fHww&auto=format&fit=crop&w=400&q=60", price: 888 },
    { id: 3, title: "Title 3", description: "Desc blabla", url: "https://images.unsplash.com/photo-1557531365-e8b22d93dbd0?ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxzZWFyY2h8OXx8d2F0Y2hlc3xlbnwwfHwwfHx8MA%3D%3D&auto=format&fit=crop&w=900&q=60", price: 888 },
    { id: 4, title: "Title 4", description: "Desc blabla", url: "https://images.unsplash.com/photo-1522312346375-d1a52e2b99b3?ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxzZWFyY2h8M3x8d2F0Y2h8ZW58MHx8MHx8fDA%3D&auto=format&fit=crop&w=400&q=60", price: 888 },
    { id: 5, title: "Title 5", description: "Desc blabla", url: "https://images.unsplash.com/photo-1533139502658-0198f920d8e8?ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxzZWFyY2h8MTB8fHdhdGNofGVufDB8fDB8fHww&auto=format&fit=crop&w=400&q=60", price: 888 },
    { id: 6, title: "Title 6", description: "Desc blabla", url: "https://images.unsplash.com/photo-1590312261344-59437f04f9ac?ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxzZWFyY2h8MTI1fHx3YXRjaHxlbnwwfHwwfHx8MA%3D%3D&auto=format&fit=crop&w=500&q=60", price: 888 },
]
</script>