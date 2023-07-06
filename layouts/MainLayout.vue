<template>
    <div id="MainHeader" class="flex items-center justify-between m-5">
        <div>
            <button>
                <Icon name="mdi:menu" size="40" />
            </button>
        </div>
        <div class="flex items-center">
            <div>Logo</div>
        </div>
        <div class="flex items-center">
            <button>
                <Icon name="mdi:search" class="ml-5" size="40"/>
            </button>
            <button>
                <Icon name="mdi:cart" class="ml-5" size="40" />
            </button>
        </div>
    </div>

    <div id="MainMenu" class="max-w-[300px] mx-auto mt-5">
        <div class="table-auto items-center justify-between">
            <ul class="flex items-center justify-between">
                <li>
                    <NuxtLink to="/collections">Collections</NuxtLink>
                </li>
                <li>
                    <NuxtLink to="/custom">Custom</NuxtLink>
                </li>
                <li>
                    <NuxtLink to="/parts">Parts</NuxtLink>
                </li>
                <li>
                    <NuxtLink to="/FAQ">FAQ</NuxtLink>
                </li>
            </ul>
        </div>
    </div>

</template>

<script setup>

</script>