<script setup>
    import MainNav from '@/Components/MainNav.vue'
    import ColorSelect from '@/Components/ColorSelect.vue';
    import { provide, ref } from 'vue';
    import { Link } from '@inertiajs/vue3';

    let width = ref('w-[250px]')
    let hide = ref(false)

    const color = ref('red')
    provide('red', color)

    function toggleWidth() {
        if(width.value == 'w-[250px]') {
            width.value = 'w-[100px]'
            hide.value = true
        }else {
            width.value = ['w-[250px]']
            hide.value = false
        }
    }
    // const isCollapsed = ref(false)

    // function toggleWidth() {
    //     isCollapsed.value = !isCollapsed.value;
    // }
</script>

<template>

<div class="flex min-h-screen">
    <div id="sidebar" class="bg-gray-900 p-6 duration-500" :class="width" style="position: relative;">
        <button class="text-xl text-gray-600" @click="toggleWidth" style="position: absolute; right: 10px; top:10px">
            <i class="fa-solid fa-bars"></i>
        </button>
        <div class="mb-6" id="branding" :hidden="hide">
            <img src="https://scontent.xx.fbcdn.net/v/t1.15752-9/376393481_3654353874810668_2387458937906500346_n.png?_nc_cat=105&ccb=1-7&_nc_sid=aee45a&_nc_eui2=AeEcpdrgZNQme6D9d3qskYm_HkKWApSL9ZseQpYClIv1mwDGNOXwun8B-htVB7GkKgN0bn8Q4EuQtcZudYAud1YC&_nc_ohc=un9q_SYxwX8AX-nKCfC&_nc_ad=z-m&_nc_cid=0&_nc_ht=scontent.xx&oh=03_AdT7WDcwDG-T_e70keP_fD8s4zOS1ikZ4RtZJPrkLMXwQg&oe=6528C5A6" alt="Logo"
                class="w-[170px] h-[170px] mx-auto rounded-full object-cover">

        </div>
        <hr class="border-gray-600" :hidden="hide">

        <!-- <div class="main-nav">
            <Link href="#">
                <i class="fa fa-home"></i> <span :class="hidden">Home</span>
            </Link>
            <Link href="#">
                <i class="fa fa-question"></i> <span :class="hidden">About Us</span>
            </Link>
            <Link href="#">
                <i class="fa-solid fa-cart-shopping"></i> <span :class="hidden">Products</span>
            </Link>
            <Link href="#">
                <i class="fa-regular fa-images"></i> <span :class="hidden">Gallery</span></Link>
            <Link href="#">
                <i class="fa-solid fa-phone-volume"></i> <span :class="hidden">Contact Us</span></Link>
        </div> -->

        <MainNav :hidden="hide"></MainNav>

        <!-- <ColorSelect></ColorSelect> -->
    </div>
    <div id="container" class="flex-1">
        <slot />
    </div>
</div>

</template>
