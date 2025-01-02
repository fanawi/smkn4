<template>
    <div class="container mx-auto p-6">
      <h1 class="text-4xl font-bold text-center mb-8">Prestasi SMK Negeri 4 Tasikmalaya</h1>
  
      <!-- Daftar Prestasi -->
      <div class="grid grid-cols-1 md:grid-cols-2 lg:grid-cols-3 gap-6">
        <div
          v-for="(prestasi, index) in paginatedPrestasi"
          :key="index"
          class="card w-full bg-base-100 shadow-xl"
        >
          <figure>
            <!-- Gambar Prestasi -->
            <img :src="prestasi.image" alt="Prestasi Image" class="w-full h-56 object-cover" />
          </figure>
          <div class="card-body">
            <h3 class="card-title text-xl font-semibold">{{ prestasi.judul }}</h3>
            <p class="text-gray-700">{{ prestasi.deskripsi }}</p>
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
  
  // Data Prestasi
  const prestasiList = ref([
    {
      judul: 'Juara 1 Lomba Debat Bahasa Indonesia',
      deskripsi: 'SMK Negeri 4 Tasikmalaya berhasil meraih juara 1 dalam lomba debat Bahasa Indonesia tingkat nasional.',
      image: 'https://via.placeholder.com/400x300?text=Debat+Bahasa+Indonesia'
    },
    {
      judul: 'Juara 2 Olimpiade Matematika',
      deskripsi: 'Siswa SMK Negeri 4 Tasikmalaya meraih juara 2 dalam olimpiade matematika tingkat provinsi.',
      image: 'https://via.placeholder.com/400x300?text=Olimpiade+Matematika'
    },
    {
      judul: 'Juara 3 Lomba Karya Tulis Ilmiah',
      deskripsi: 'Siswa kami berhasil meraih juara 3 dalam lomba karya tulis ilmiah tingkat daerah.',
      image: 'https://via.placeholder.com/400x300?text=Lomba+Karya+Tulis'
    },
    {
      judul: 'Juara 1 Lomba Cerdas Cermat',
      deskripsi: 'SMK Negeri 4 Tasikmalaya menjuarai lomba cerdas cermat tingkat kabupaten.',
      image: 'https://via.placeholder.com/400x300?text=Lomba+Cerdas+Cermat'
    },
    {
      judul: 'Juara 2 Olimpiade Fisika',
      deskripsi: 'Siswa kami meraih juara 2 dalam olimpiade fisika tingkat provinsi.',
      image: 'https://via.placeholder.com/400x300?text=Olimpiade+Fisika'
    },
    {
      judul: 'Juara 3 Lomba Desain Grafis',
      deskripsi: 'Siswa kami berhasil meraih juara 3 dalam lomba desain grafis.',
      image: 'https://via.placeholder.com/400x300?text=Lomba+Desain+Grafis'
    },
    {
      judul: 'Juara 1 Lomba Karya Tulis Ilmiah',
      deskripsi: 'SMK Negeri 4 Tasikmalaya berhasil meraih juara 1 dalam lomba karya tulis ilmiah tingkat nasional.',
      image: 'https://via.placeholder.com/400x300?text=Lomba+Karya+Tulis+Ilmiah'
    },
    {
      judul: 'Juara 1 Lomba Seni Tari',
      deskripsi: 'Siswa kami meraih juara 1 dalam lomba seni tari tingkat kabupaten.',
      image: 'https://via.placeholder.com/400x300?text=Lomba+Seni+Tari'
    }
  ]);
  
  // Pagination State
  const currentPage = ref(1);
  const itemsPerPage = 4; // 4 card per halaman
  
  // Menghitung total halaman
  const totalPages = computed(() => Math.ceil(prestasiList.value.length / itemsPerPage));
  
  // Mengambil data yang akan ditampilkan berdasarkan halaman
  const paginatedPrestasi = computed(() => {
    const start = (currentPage.value - 1) * itemsPerPage;
    const end = currentPage.value * itemsPerPage;
    return prestasiList.value.slice(start, end);
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
  