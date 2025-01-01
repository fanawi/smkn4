<template>
    <div class="container mx-auto p-6">
      <h1 class="text-4xl font-bold text-center mb-8">Ekstrakurikuler SMK Negeri 4 Tasikmalaya</h1>
  
      <!-- Daftar Ekstrakurikuler -->
      <div class="grid grid-cols-1 md:grid-cols-2 lg:grid-cols-4 gap-6">
        <div v-for="(ekstra, index) in paginatedEkstrakurikuler" :key="index" class="card w-full bg-base-100 shadow-xl">
          <figure class="flex justify-center">
            <!-- Logo Ekstrakurikuler -->
            <img :src="ekstra.logo" alt="Logo Ekstrakurikuler" class="w-24 h-24 object-contain mt-4" />
          </figure>
          <figure>
            <!-- Gambar Ekstrakurikuler -->
            <img :src="ekstra.image" alt="Ekstrakurikuler Image" class="w-full h-38 object-cover" />
          </figure>
          <div class="card-body">
            <h3 class="card-title text-xl font-semibold">{{ ekstra.nama }}</h3>
            <p class="text-gray-700">{{ ekstra.deskripsi }}</p>
            <div class="card-actions justify-end">
              <button class="btn btn-primary">Detail</button>
            </div>
          </div>
        </div>
      </div>
  
      <!-- Pagination Controls -->
      <div class="mt-6 flex justify-center">
        <button
          @click="previousPage"
          class="btn btn-primary mx-2"
          :disabled="currentPage === 1"
        >
          Previous
        </button>
        <span class="mx-2 font-semibold">Page {{ currentPage }} of {{ totalPages }}</span>
        <button
          @click="nextPage"
          class="btn btn-primary mx-2"
          :disabled="currentPage === totalPages"
        >
          Next
        </button>
      </div>
    </div>
  </template>
  
  <script setup>
  import { ref, computed } from 'vue';
  
  // Data Ekstrakurikuler
  const ekstrakurikulerData = ref([
    {
      nama: 'Basket',
      deskripsi: 'Ekstrakurikuler Basket untuk melatih fisik dan kerjasama tim dalam permainan bola basket.',
      image: 'https://via.placeholder.com/400x300?text=Basket',
      logo: 'https://via.placeholder.com/100x100?text=Logo+Basket'
    },
    {
      nama: 'Volleyball',
      deskripsi: 'Ekstrakurikuler Volleyball yang mengasah kemampuan teknik dan strategi dalam permainan bola voli.',
      image: 'https://via.placeholder.com/400x300?text=Volleyball',
      logo: 'https://via.placeholder.com/100x100?text=Logo+Volleyball'
    },
    {
      nama: 'Paskibra',
      deskripsi: 'Ekstrakurikuler Paskibra yang mengembangkan kedisiplinan dan keterampilan dalam baris berbaris.',
      image: 'https://via.placeholder.com/400x300?text=Paskibra',
      logo: 'https://via.placeholder.com/100x100?text=Logo+Paskibra'
    },
    {
      nama: 'Pramuka',
      deskripsi: 'Ekstrakurikuler Pramuka yang bertujuan membentuk karakter dan kemandirian para siswa.',
      image: 'https://via.placeholder.com/400x300?text=Pramuka',
      logo: 'https://via.placeholder.com/100x100?text=Logo+Pramuka'
    },
    {
      nama: 'Band',
      deskripsi: 'Ekstrakurikuler Band yang memberikan kesempatan bagi siswa untuk mengembangkan bakat musik.',
      image: 'https://via.placeholder.com/400x300?text=Band',
      logo: 'https://via.placeholder.com/100x100?text=Logo+Band'
    },
    {
      nama: 'Drama',
      deskripsi: 'Ekstrakurikuler Drama yang mengasah keterampilan berakting, kreativitas, dan kerjasama tim.',
      image: 'https://via.placeholder.com/400x300?text=Drama',
      logo: 'https://via.placeholder.com/100x100?text=Logo+Drama'
    },
    {
      nama: 'Futsal',
      deskripsi: 'Ekstrakurikuler Futsal yang melatih skill sepak bola dan kerja tim.',
      image: 'https://via.placeholder.com/400x300?text=Futsal',
      logo: 'https://via.placeholder.com/100x100?text=Logo+Futsal'
    },
    {
      nama: 'Badminton',
      deskripsi: 'Ekstrakurikuler Badminton yang mengasah teknik dan kecepatan dalam olahraga bulu tangkis.',
      image: 'https://via.placeholder.com/400x300?text=Badminton',
      logo: 'https://via.placeholder.com/100x100?text=Logo+Badminton'
    }
  ]);
  
  // Pagination State
  const currentPage = ref(1);
  const itemsPerPage = 4; // Mengubah jumlah card per halaman menjadi 4
  
  // Menghitung total halaman
  const totalPages = computed(() => Math.ceil(ekstrakurikulerData.value.length / itemsPerPage));
  
  // Mengambil data yang akan ditampilkan berdasarkan halaman
  const paginatedEkstrakurikuler = computed(() => {
    const start = (currentPage.value - 1) * itemsPerPage;
    const end = currentPage.value * itemsPerPage;
    return ekstrakurikulerData.value.slice(start, end);
  });
  
  // Fungsi untuk halaman sebelumnya
  const previousPage = () => {
    if (currentPage.value > 1) {
      currentPage.value--;
    }
  };
  
  // Fungsi untuk halaman berikutnya
  const nextPage = () => {
    if (currentPage.value < totalPages.value) {
      currentPage.value++;
    }
  };
  </script>
  
  <style scoped>
  /* Optional styling */
  </style>
  