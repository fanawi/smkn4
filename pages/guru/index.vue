<template>
    <div class="container mx-auto p-6">
      <h1 class="text-4xl font-bold text-center mb-8">Daftar Guru dan Staff SMK Negeri 4 Tasikmalaya</h1>
  
      <!-- Filter dan Pencarian -->
      <div class="mb-6 flex justify-center">
        <input
          v-model="searchQuery"
          type="text"
          class="input input-bordered input-primary w-64"
          placeholder="Cari Guru atau Staff"
        />
      </div>
  
      <!-- Daftar Guru dan Staff -->
      <div class="grid grid-cols-1 md:grid-cols-2 lg:grid-cols-3 gap-6">
        <div
          v-for="person in filteredStaff"
          :key="person.id"
          class="card w-full bg-base-100 shadow-xl"
        >
          <figure>
            <img
              :src="person.photo"
              alt="Person"
              class="w-full h-48 object-cover"
            />
          </figure>
          <div class="card-body">
            <h2 class="card-title">{{ person.name }}</h2>
            <p><strong>Jabatan:</strong> {{ person.position }}</p>
          </div>
        </div>
      </div>
    </div>
  </template>
  
  <script setup>
  import { ref, computed } from 'vue';
  
  // Daftar data guru dan staff
  const staff = [
    {
      id: 1,
      name: 'Kurniawan, S.Pd, M.Pd.',
      position: 'Kepala Sekolah',
      photo: 'https://via.placeholder.com/400',
    },
    {
      id: 2,
      name: 'Hendri Kuswandi, S.Pd.',
      position: 'Guru Teknik Otomotif',
      photo: 'https://via.placeholder.com/400',
    },
    {
      id: 3,
      name: 'Siti Aminah, S.Kom.',
      position: 'Guru Teknik Komputer dan Informatika',
      photo: 'https://via.placeholder.com/400',
    },
    {
      id: 4,
      name: 'Rizki Ramadhan, S.Pd.',
      position: 'Guru Bahasa Inggris',
      photo: 'https://via.placeholder.com/400',
    },
  ];
  
  // Untuk pencarian
  const searchQuery = ref('');
  
  // Computed property untuk menyaring data berdasarkan nama atau jabatan
  const filteredStaff = computed(() => {
    return staff.filter(person => {
      return (
        person.name.toLowerCase().includes(searchQuery.value.toLowerCase()) ||
        person.position.toLowerCase().includes(searchQuery.value.toLowerCase())
      );
    });
  });
  </script>
  
  <style scoped>
  /* Optional: Custom styling */
  </style>
  