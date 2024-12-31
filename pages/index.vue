<template>
    <div class=" carousel w-full z-20 relative">
        <!-- Carousel Items -->
        <div v-for="(item, index) in items" :key="index"
            :class="['carousel-item w-full', { 'active': currentSlide === index }]"
            style="transition: transform 2s ease-in-out;">
            <!-- Background Image -->
            <img :src="item.img" class="w-full h-[80vh] opacity-60 object-cover" />

            <!-- Text Content -->
            <div class="absolute inset-0 flex flex-col items-center justify-center text-center text-white z-10 px-4">
                <h1 class="text-4xl md:text-5xl font-bold mb-4">{{ item.title }}</h1>
                <p class="text-base md:text-lg max-w-2xl">{{ item.description }}</p>
            </div>

            <!-- Foreground Image -->
        </div>

        <!-- Previous Button -->
        <button
            class="prev group absolute top-1/2 left-4 transform -translate-y-1/2 border border-white text-white hover:bg-[#11224e] hover:text-white flex p-2 rounded-full z-20"
            @click="prevSlide">
            <Icon name="material-symbols:arrow-left-alt-rounded" size="2rem" class="group-hover:scale-75" />
        </button>

        <!-- Next Button -->
        <button
            class="next group absolute top-1/2 right-4 transform -translate-y-1/2 border border-white text-white hover:bg-[#11224e] hover:text-white flex p-2 rounded-full z-20"
            @click="nextSlide">
            <Icon name="material-symbols:arrow-right-alt-rounded" size="2rem" class="group-hover:scale-75" />
        </button>
    </div>

    <div class="hero bg-base-300 min-h-screen text-white">
        <div class="hero-content flex">
            <div class="flex-cols">
                <img src="../assets/img/kepsek.png" class="max-w-sm rounded-lg shadow-2xl" />
                <div class="Text text-center font-bold bg-gradient-to-r from-blue-900 via-blue-700 to-blue-500  text-white rounded-lg py-2 leading-3">
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
    <div class="hero  min-h-screen text-white">
        <div class="hero-content flex-col lg:flex-row-reverse">
            <img src="../assets/img/ruangkelas1.jpg " class="max-w-sm rounded-lg shadow-2xl" />
            <div>
                <h1 class="text-5xl font-bold">Sejarah Sekolah</h1>
                <p class="py-6 text-justify">
                    Sejalan dengan Program Pemerintah dibidang pendidikan Menengah Kejuruan pada saat itu yakni
                    pemerataan akses ditambah pula dengan banyaknya keinginan masyarakat yang mengharapkan adanya SMK
                    Negeri di daerah Kecamatan Purbaratu Kota Tasikmalaya terutama untuk menampung tamatan dari SLTP
                    yang ingin melanjutkan ke SMK maka beberapa tokoh masyarakat, unsur pejabat pemerintah di Kecamatan
                    Purbaratu Kota Tasikmalaya mengusulkan kepada pemerintah Kota Tasikmalaya dan Pemerintah Provinsi
                    Jawa Barat, agar berdirinya SMK Negeri di Kecamatan Purbaratu Kota Tasikmalaya.
                </p>
                <button class="btn btn-outline btn-success">
                    <NuxtLink to="../sejarah"><p class="">Selengkapnya ...</p></NuxtLink>
                </button>
            </div>
        </div>
    </div>
</template>

<script setup>
import images1 from '../assets/img/gerbangsmk.png';
import images4 from '../assets/img/TP.jpg';
import images5 from '../assets/img/pbo.png';
import images6 from '../assets/img/pp.jpeg';
import images7 from '../assets/img/ruangkelas1.jpg'

const items = ref([
  { bg: images1, img: images1, title: 'Judul Slide 1', description: 'Deskripsi untuk slide pertama.' },
  { bg: images1, img: images7, title: 'Judul Slide 2', description: 'Deskripsi untuk slide kedua.' },
  { bg: images1, img: images6, title: 'Judul Slide 3', description: 'Deskripsi untuk slide ketiga.' },
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