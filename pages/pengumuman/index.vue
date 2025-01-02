<template>
    <div class="container mx-auto p-6">
      <h1 class="text-4xl font-bold text-center mb-8">Pengumuman Terbaru</h1>
  
      <!-- Daftar Pengumuman -->
      <div class="space-y-6">
        <div v-for="announcement in announcements" :key="announcement.id">
          <div class="card bg-base-100 shadow-xl">
            <div class="card-body">
              <h2 class="card-title">{{ announcement.title }}</h2>
              <p>{{ announcement.content }}</p>
              <div class="card-actions justify-end">
                <a :href="announcement.link" class="btn btn-primary" target="_blank">Baca Selengkapnya</a>
              </div>
            </div>
          </div>
        </div>
      </div>
    </div>
  </template>
  
  <script setup>
  // Data pengumuman
  const announcements = [
    {
      id: 1,
      title: 'Pengumuman 1: Pembukaan Pendaftaran Siswa Baru',
      content: 'Pendaftaran siswa baru dibuka mulai hari ini. Segera daftarkan diri Anda!',
      link: 'https://www.example.com/announcement1',
    },
    {
      id: 2,
      title: 'Pengumuman 2: Libur Semester',
      content: 'Libur semester akan dimulai pada 5 Januari hingga 15 Januari.',
      link: 'https://www.example.com/announcement2',
    },
    {
      id: 3,
      title: 'Pengumuman 3: Ujian Tengah Semester',
      content: 'Jadwal ujian tengah semester akan diumumkan minggu depan.',
      link: 'https://www.example.com/announcement3',
    },
  ];
  </script>
  
  <style scoped>
  /* Optional: Custom styling if necessary */
  </style>
  