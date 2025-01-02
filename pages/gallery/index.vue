<template>
    <div class="p-4">
        <h1 class="text-3xl text-center mb-8">Galeri Foto</h1>
        <div class="grid grid-cols-1 sm:grid-cols-2 md:grid-cols-3 gap-6">
            <div v-for="(image, index) in images" :key="index"
                class="overflow-hidden rounded-lg shadow-lg group transform hover:scale-105 transition-transform duration-300">
                <img :src="image.src" :alt="image.alt"
                    class="w-full h-64 object-cover group-hover:scale-110 transition-transform duration-300" />
            </div>
        </div>
    </div>
</template>

<script setup>
import ffImage from '@/assets/img/ff.png';
import d from '@/assets/img/ff.png';
import f from '@/assets/img/ff.png';

const images = [
    { src: ffImage, alt: 'Image 1' },
    { src: d, alt: 'Image 2' },
    { src: f, alt: 'Image 3' },
];
</script>

<style scoped>
/* Tambahkan gaya tambahan jika diperlukan */
</style>