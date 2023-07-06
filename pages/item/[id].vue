<template>
    <MainLayout />
    <div class="flex mt-10">
        <div class="mx-auto">
            <!-- display a big image of the watch -->
            <img :src="currentImage" class="rounded-t w-full object-contain
            " alt="">

        </div>
    </div>
    <div class="flex mt-10 text-5xl">
        <div class="mx-auto">
            The goat
        </div>
    </div>

    <div class="flex mt-7">
        <div class="mx-10">
            Introducing the Goat, a sophisticated timekeeping marvel that seamlessly combines precision, elegance, and
            functionality. This remarkable timepiece merges the precision of a mechanical chronograph with the practicality
            of a calendar feature, resulting in a truly versatile and captivating horological companion.
        </div>
    </div>

    <div class="flex mt-7 mb-10">
        <div class="mx-10">
            Immerse yourself in the world of horological excellence with this Mechanical Chronotimer with Calendar Function,
            where technical precision and stylish sophistication converge to redefine your perception of timekeeping.
        </div>
    </div>

    <div v-for="(header, index) in headers" :key="header.title">
        <button @click="handleAccordion(index)" class="mx-10 text-2xl">
            {{ header.title }}
        </button>
        <!-- make this list show the bullet points and not so flushed to the left -->
        <Collapse :when="headers[index].isExpanded" class="v-collapse">
            <ol>
                <li v-for="body in header.body">
                    {{ body }}
                </li>
            </ol>

        </Collapse>
    </div>
</template>

<script setup>
import { reactive } from 'vue'

const headers = reactive([
    {
        title: 'Specifications',
        body: ["Miyota 90S5", "Automatic movement (no-date), 28800 bph"],
        isExpanded: false // Initial value
    },
    {
        title: 'Dimensions',
        body: ["39mm case width", "47mm lug-to-lug"],
        isExpanded: false
    },
    {
        title: 'Care',
        body: ["Don't drop it"],
        isExpanded: false
    }
])

function handleAccordion(selectedIndex) {
    headers.forEach((_, index) => {
        headers[index].isExpanded = index === selectedIndex ? !headers[index].isExpanded : false
    })
}

import MainLayout from '@/layouts/MainLayout.vue';
import { ref, watchEffect, onMounted } from 'vue'
import { Collapse } from 'vue-collapsed'
const isOpen = ref(false)

let currentImage = ref(null)
onMounted(() => {
    watchEffect(() => {
        currentImage.value = 'https://images.unsplash.com/photo-1524805444758-089113d48a6d?ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D&auto=format&fit=crop&w=688&q=80',
            images.value[0] = 'https://images.unsplash.com/photo-1524805444758-089113d48a6d?ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D&auto=format&fit=crop&w=688&q=80'
    })
})

const images = ref([
    'https://images.unsplash.com/photo-1490915785914-0af2806c22b6?ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxzZWFyY2h8MTJ8fHdhdGNoJTIwaXdjfGVufDB8fDB8fHww&auto=format&fit=crop&w=900&q=60',
    'https://images.unsplash.com/photo-1495856458515-0637185db551?ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxzZWFyY2h8MjR8fHdhdGNoJTIwaXdjfGVufDB8fDB8fHww&auto=format&fit=crop&w=900&q=60',
    'https://images.unsplash.com/photo-1511370235399-1802cae1d32f?ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxzZWFyY2h8MzN8fHdhdGNoJTIwaXdjfGVufDB8fDB8fHww&auto=format&fit=crop&w=900&q=60'
])

const specifications = ref([
    'Miyota 90S5 automatic movement (no-date), 28800 bph',
    'Screw-down crown'
])

const dimensions = ref([
    '39mm case width',
    '47mm lug-to-lug',
])

function handleCollapse() {
    isOpen.value = !isOpen.value
}

</script>