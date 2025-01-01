<template>
    <div class="container mx-auto p-6">
      <h1 class="text-4xl font-bold text-center mb-8">Kompetensi Keahlian (Jurusan) SMK Negeri 4 Tasikmalaya</h1>
  
      <!-- Daftar Jurusan -->
      <div class="grid grid-cols-1 md:grid-cols-2 lg:grid-cols-3 gap-6">
        <div
          v-for="(jurusan, index) in jurusanList"
          :key="index"
          class="card w-full bg-base-100 shadow-xl"
        >
          <figure>
            <!-- Gambar Jurusan -->
            <img :src="jurusan.image" alt="Jurusan Image" class="w-full h-56 object-cover" />
          </figure>
          <div class="card-body">
            <h3 class="card-title text-xl font-semibold">{{ jurusan.nama }}</h3>
            <p class="text-gray-700">{{ jurusan.deskripsi }}</p>
            <div class="mt-4">
              <a :href="jurusan.link" target="_blank" class="btn btn-primary">Pelajari Lebih Lanjut</a>
            </div>
          </div>
        </div>
      </div>
    </div>
  </template>
  
  <script setup>
  import { ref } from 'vue';
  
  // Data Jurusan
  const jurusanList = ref([
    {
      nama: 'Teknik Otomotif',
      deskripsi: 'Program keahlian yang mempersiapkan siswa untuk memahami dunia otomotif dan perawatan kendaraan bermotor.',
      image: 'https://via.placeholder.com/400x300?text=Teknik+Otomotif',
      link: '#'
    },
    {
      nama: 'Teknik Komputer dan Informatika',
      deskripsi: 'Program keahlian yang mengajarkan siswa untuk mengembangkan keterampilan di bidang teknologi informasi dan komputer.',
      image: 'https://via.placeholder.com/400x300?text=Teknik+Komputer+dan+Informatika',
      link: '#'
    },
    {
      nama: 'Desain Komunikasi Visual',
      deskripsi: 'Jurusan ini memfokuskan siswa pada pengembangan keterampilan desain grafis dan komunikasi visual.',
      image: 'https://via.placeholder.com/400x300?text=Desain+Komunikasi+Visual',
      link: '#'
    },
    {
      nama: 'Akuntansi dan Keuangan Lembaga',
      deskripsi: 'Program keahlian yang mengajarkan siswa dalam bidang akuntansi dan pengelolaan keuangan.',
      image: 'https://via.placeholder.com/400x300?text=Akuntansi+dan+Keuangan',
      link: '#'
    },
    {
      nama: 'Pemasaran',
      deskripsi: 'Jurusan ini mempersiapkan siswa dengan keterampilan dalam bidang pemasaran, penjualan, dan bisnis.',
      image: 'https://via.placeholder.com/400x300?text=Pemasaran',
      link: '#'
    },
    {
      nama: 'Perhotelan',
      deskripsi: 'Jurusan yang mempersiapkan siswa untuk bekerja di industri perhotelan dan pariwisata.',
      image: 'https://via.placeholder.com/400x300?text=Perhotelan',
      link: '#'
    }
  ]);
  </script>
  
  <style scoped>
  /* Optional styling */
  </style>
  