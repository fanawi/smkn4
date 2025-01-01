<template>
  <div class="container mx-auto p-6">
    <h1 class="text-4xl font-bold text-center mb-8">Data Statistik SMK Negeri 4 Tasikmalaya</h1>

    <!-- Statistik -->
    <div class="grid grid-cols-1 md:grid-cols-2 lg:grid-cols-3 gap-6">
      <!-- Jumlah Siswa -->
      <div class="card w-full bg-base-100 shadow-xl">
        <div class="card-body">
          <h2 class="card-title text-center">Jumlah Siswa</h2>
          <p class="text-3xl font-bold text-center">{{ studentCount }}</p>
          <div class="card-actions justify-center mt-4">
            <button class="btn btn-primary btn-sm">Lihat Detail</button>
          </div>
        </div>
      </div>

      <!-- Jumlah Guru -->
      <div class="card w-full bg-base-100 shadow-xl">
        <div class="card-body">
          <h2 class="card-title text-center">Jumlah Guru</h2>
          <p class="text-3xl font-bold text-center">{{ teacherCount }}</p>
          <div class="card-actions justify-center mt-4">
            <button class="btn btn-primary btn-sm">Lihat Detail</button>
          </div>
        </div>
      </div>

      <!-- Akreditasi -->
      <div class="card w-full bg-base-100 shadow-xl">
        <div class="card-body">
          <h2 class="card-title text-center">Akreditasi</h2>
          <p class="text-3xl font-bold text-center">{{ accreditation }}</p>
          <div class="card-actions justify-center mt-4">
            <button class="btn btn-primary btn-sm">Lihat Detail</button>
          </div>
        </div>
      </div>

      <!-- Luas Tanah -->
      <div class="card w-full bg-base-100 shadow-xl">
        <div class="card-body">
          <h2 class="card-title text-center">Luas Tanah</h2>
          <p class="text-3xl font-bold text-center">{{ landArea }} m²</p>
          <div class="card-actions justify-center mt-4">
            <button class="btn btn-primary btn-sm">Lihat Detail</button>
          </div>
        </div>
      </div>

      <!-- Jumlah Ruangan -->
      <div class="card w-full bg-base-100 shadow-xl">
        <div class="card-body">
          <h2 class="card-title text-center">Jumlah Ruangan</h2>
          <p class="text-3xl font-bold text-center">{{ roomCount }}</p>
          <div class="card-actions justify-center mt-4">
            <button class="btn btn-primary btn-sm">Lihat Detail</button>
          </div>
        </div>
      </div>

      <!-- Tahun Pendirian -->
      <div class="card w-full bg-base-100 shadow-xl">
        <div class="card-body">
          <h2 class="card-title text-center">Tahun Pendirian</h2>
          <p class="text-3xl font-bold text-center">{{ establishmentYear }}</p>
          <div class="card-actions justify-center mt-4">
            <button class="btn btn-primary btn-sm">Lihat Detail</button>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script setup>
// Data statistik
const studentCount = 1200; // Jumlah siswa
const teacherCount = 50; // Jumlah guru
const accreditation = 'A (Unggul)'; // Akreditasi
const landArea = 13229; // Luas tanah dalam meter persegi
const roomCount = 40; // Jumlah ruangan
const establishmentYear = 2010; // Tahun pendirian
</script>

<style scoped>
/* Optional: Custom styling */
</style>
