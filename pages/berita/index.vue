<template>
    <div class="p-4">
      <h1 class="text-4xl font-bold text-center mb-6">Berita Terbaru</h1>
      
      <div class="grid grid-cols-1 md:grid-cols-2 lg:grid-cols-3 gap-6">
        <div
          v-for="(article, index) in articles"
          :key="index"
          class="card w-full bg-base-100 shadow-xl"
        >
          <figure>
            <img :src="article.image" alt="Article Image" class="w-full h-64 object-cover" />
          </figure>
          <div class="card-body">
            <h2 class="card-title">{{ article.title }}</h2>
            <p>{{ article.description }}</p>
            <div class="card-actions justify-end">
              <button class="btn btn-primary">
                <NuxtLink :to="'/berita/' + article.id">Baca Selengkapnya</NuxtLink>
              </button>
            </div>
          </div>
        </div>
      </div>
    </div>
  </template>
  
  <script setup>
  const articles = [
    {
      id: 1,
      title: 'Berita 1: Teknologi Terbaru',
      description: 'Deskripsi singkat tentang teknologi terbaru yang mempengaruhi dunia.',
      image: 'https://via.placeholder.com/400',
    },
    {
      id: 2,
      title: 'Berita 2: Pendidikan dan Perubahan',
      description: 'Berita tentang bagaimana sistem pendidikan mengalami transformasi digital.',
      image: 'https://via.placeholder.com/400',
    },
    {
      id: 3,
      title: 'Berita 3: Inovasi dalam Dunia Kesehatan',
      description: 'Inovasi terbaru dalam dunia kesehatan untuk mengatasi pandemi.',
      image: 'https://via.placeholder.com/400',
    },
  ];
  </script>
  
  <style scoped>
  /* Optional: Custom styling */
  </style>
  