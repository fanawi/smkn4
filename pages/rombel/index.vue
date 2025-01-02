<template>
    <div class="container mx-auto p-6">
      <h1 class="text-4xl font-bold text-center mb-8">Rombongan Belajar SMK Negeri 4 Tasikmalaya</h1>
  
      <!-- Daftar Jurusan -->
      <div v-for="(jurusan, index) in jurusanData" :key="index" class="mb-12">
        <h2 class="text-3xl font-semibold text-blue-600 mb-6">{{ jurusan.nama }}</h2>
  
        <!-- Rombongan Belajar -->
        <div v-if="jurusan.rombongan.length > 0" class="grid grid-cols-1 md:grid-cols-2 lg:grid-cols-3 gap-6">
          <div v-for="(rombongan, idx) in jurusan.rombongan" :key="idx" class="card w-full bg-base-100 shadow-xl">
            <div class="card-body">
              <h3 class="card-title text-xl font-semibold">{{ rombongan.namaRombongan }}</h3>
              <p class="text-gray-700">Wali Kelas: {{ rombongan.waliKelas }}</p>
              <p class="text-gray-500">Jumlah Siswa: {{ rombongan.jumlahSiswa }}</p>
              <div class="card-actions justify-end">
                <button class="btn btn-primary">Detail</button>
              </div>
            </div>
          </div>
        </div>
        <div v-else>
          <p class="text-gray-500">Tidak ada rombongan belajar untuk jurusan ini.</p>
        </div>
      </div>
    </div>
  </template>
  
  <script setup>
  // Data Jurusan dan Rombongan Belajar
  const jurusanData = [
    {
      nama: 'Teknik Otomotif',
      rombongan: [
        {
          namaRombongan: 'Rombongan A - Kelas 10',
          waliKelas: 'Budi Santoso, S.Pd.',
          jumlahSiswa: 35,
        },
        {
          namaRombongan: 'Rombongan B - Kelas 10',
          waliKelas: 'Siti Aisyah, S.Pd.',
          jumlahSiswa: 30,
        }
      ]
    },
    {
      nama: 'Teknik Komputer dan Informatika',
      rombongan: [
        {
          namaRombongan: 'Rombongan A - Kelas 11',
          waliKelas: 'Kurniawan, S.Pd.',
          jumlahSiswa: 32,
        },
        {
          namaRombongan: 'Rombongan B - Kelas 11',
          waliKelas: 'Fajar, S.Pd.',
          jumlahSiswa: 28,
        }
      ]
    }
  ];
  </script>
  
  <style scoped>
  /* Optional styling for cards */
  </style>
        