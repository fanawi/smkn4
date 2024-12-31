<template>
    <div class="hero">
        <img src="../assets/img/gerbangsmk.png" class="min-h-screen">
        <div class="hero-overlay carousel bg-opacity-60"></div>
        <div class="hero-content text-neutral-content text-center">
            <div class="max-w-md">
                <h1 class="mb-5 text-4xl font-bold">Welcome to Website <br>SMK Negeri 4 Tasikmalaya</h1>
                <p class="mb-5">
                    <icon name="ph:copyright" /> Made by Fahrul Nabawi Agustin
                </p>
                <button class="btn btn-primary">Get Started</button>
            </div>
        </div>
    </div>
    <div class="paddinX carousel w-full z-20 mt-2 relative">
        <!-- Carousel Items -->
        <div v-for="(item, index) in items" :key="index"
            :class="['carousel-item w-full', { 'active': currentSlide === index }]"
            style="transition: transform 0.5s ease-in-out;">
            <img :src="item.bg" class="w-full h-[80vh] opacity-15" />
            <div class="absolute bottom-0">
                <img :src="item.img" alt="" />
            </div>
        </div>

        <!-- Previous Button -->
        <button
            class="prev group absolute top-1/2 left-4 transform -translate-y-1/2 border border-[#11224e] text-[#11224e] hover:bg-[#11224e] hover:text-white flex p-2 rounded-full z-20"
            @click="prevSlide">
            <Icon name="material-symbols:arrow-left-alt-rounded" size="2rem" class="group-hover:scale-75" />
        </button>

        <!-- Next Button -->
        <button
            class="next group absolute top-1/2 right-4 transform -translate-y-1/2 border border-[#11224e] text-[#11224e] hover:bg-[#11224e] hover:text-white flex p-2 rounded-full z-20"
            @click="nextSlide">
            <Icon name="material-symbols:arrow-right-alt-rounded" size="2rem" class="group-hover:scale-75" />
        </button>
    </div>

    <div class="hero bg-base-500 min-h-screen">
        <div class="hero-content flex">
            <div class="flex-cols">
                <img src="../assets/img/KepalaSekolah.png" class="max-w-sm rounded-lg shadow-2xl" />
                <div class="Text text-center font-bold bg-green-800 text-black rounded-lg py-2 leading-3">
                    <p class="tracking-wide text-2xl">Kurniawan, S.Pd., M.Pd.</p>
                    <p class="tracking-wide text-lg">Kepala Sekolah</p>
                </div>
            </div>
            <div class="ml-4">
                <h1 class="text-5xl font-bold mb-4">Sambutan Kepala Sekolah</h1>
                <p>Assalamu'alaikum Wr, Wb</p>
                <br />
                <p>
                    Puji syukur kita panjatkan ke hadirat Allah SWT atas limpahan rahmat dan karunia-Nya, sehingga SMKN
                    4
                    Tasikmalaya dapat terus berkiprah dalam mencetak generasi muda yang unggul, berkarakter, dan siap
                    bersaing
                    di dunia kerja maupun melanjutkan pendidikan ke jenjang yang lebih tinggi.
                </p>
                <br />
                <p>
                    Selamat datang di situs resmi SMKN 4 Tasikmalaya, sebuah media informasi yang kami persembahkan
                    untuk
                    memberikan gambaran menyeluruh mengenai sekolah kami. Situs ini dirancang untuk memudahkan akses
                    informasi
                    bagi seluruh siswa, orang tua, alumni, dan masyarakat luas.
                </p>
            </div>
        </div>

    </div>
</template>

<script setup>
import images1 from '../assets/img/gerbangsmk.png';
import images4 from '../assets/img/TP.jpg';
import images5 from '../assets/img/pbo.png';
import images6 from '../assets/img/pp.jpeg';

const items = ref([
    { bg: images1, img: images4 },
    { bg: images1, img: images5 },
    { bg: images1, img: images6 },
]);

const currentSlide = ref(0);
let interval = null;

// Navigate to the next slide
const nextSlide = () => {
    currentSlide.value = (currentSlide.value + 1) % items.value.length;
};

// Navigate to the previous slide
const prevSlide = () => {
    currentSlide.value = (currentSlide.value - 1 + items.value.length) % items.value.length;
};

// Auto-scroll the slides
const startAutoScroll = () => {
    interval = setInterval(nextSlide, 5000); // 5 seconds
};

// Stop auto-scroll
const stopAutoScroll = () => {
    if (interval) clearInterval(interval);
};

// Lifecycle hooks
onMounted(() => {
    startAutoScroll();
});

onUnmounted(() => {
    stopAutoScroll();
});
</script>

<style scoped>
.carousel-item {
    display: none;
}

.carousel-item.active {
    display: block;
}
</style>