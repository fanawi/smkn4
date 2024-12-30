<template>
  <div class="relative z-50">
    <header class="bg-gradient-to-r paddingX from-blue-900 via-blue-700 to-blue-500 text-white shadow-md">
      <div class="container px-6 py-4 mx-auto flex justify-between items-center">
        <!-- Logo -->
        <div class="flex items-center space-x-2">
          <img src="../assets/img/Logo.png" alt="Logo" class="h-[80px]" />
          <div class="">
            <h1 class="text-3xl font-bold text-black ">SMK Negeri 4 Tasikmalaya</h1>
            <address> Jl. Depok Sukamenak, Purbaratu,Tasikmalaya, Jawa Barat, Indonesia</address>
          </div>
        </div>
        <div class="paddingX bg flex justify-center text-black paddingX  font-titillium gap-6 sticky py-3">
          <NuxtLink to="/">
            <p class="">Beranda</p>
          </NuxtLink>
          <div class="Profile relative inline-block group cursor-pointer">
            <div class="OnHover group flex items-center">
              <p class="">Profil Sekolah</p>
              <Icon name="material-symbols:keyboard-arrow-down-rounded" class="group-hover:rotate-180" />
            </div>
            <div
              class="ListHover absolute left-0 z-10 hidden origin-top-right bg-white shadow-md w-[150px] divide-y divide-gray-100 group-hover:block group-hover:transition-all group-hover:ease-in-out group-hover:duration-300">
              <ul>
                <li class="hover:bg-slate-100 p-2">Sejarah</li>
                <li class="hover:bg-slate-100 p-2">Visi dan Misi</li>
                <li class="hover:bg-slate-100 p-2">Identitas Sekolah</li>
                <li class="hover:bg-slate-100 p-2">Struktur Organisasi</li>
                <li class="hover:bg-slate-100 p-2">Guru dan Staff</li>
                <li class="hover:bg-slate-100 p-2">Data Statistik</li>
              </ul>
            </div>
          </div>
          <div class="Siswa relative inline-block group cursor-pointer">
            <div class="OnHover group flex items-center">
              <p class="">Siswa</p>
              <Icon name="material-symbols:keyboard-arrow-down-rounded" class="group-hover:rotate-180" />
            </div>
            <div
              class="ListHover absolute left-0 z-10 hidden origin-top-right bg-white shadow-md w-[150px] divide-y divide-gray-100 group-hover:block group-hover:transition-all group-hover:ease-in-out group-hover:duration-300">
              <ul>
                <li class="hover:bg-slate-100 p-2">Rombongan Belajar</li>
                <li class="hover:bg-slate-100 p-2">Ekstrakurikuler</li>
                <li class="hover:bg-slate-100 p-2">Prestasi</li>
                <li class="hover:bg-slate-100 p-2">Kompetensi Keahlian</li>
              </ul>
            </div>
          </div>
          <div class="Artikel relative inline-block group cursor-pointer">
            <div class="OnHover group flex items-center">
              <p title="Artikel" class="">Informasi</p>
              <Icon name="material-symbols:keyboard-arrow-down-rounded" class="group-hover:rotate-180" />
            </div>
            <div
              class="ListHover absolute left-0 z-10 hidden origin-top-right bg-white shadow-md w-[150px] divide-y divide-gray-100 group-hover:block group-hover:transition-all group-hover:ease-in-out group-hover:duration-300">
              <ul>
                <li class="hover:bg-slate-100 p-2">Berita</li>
                <li class="hover:bg-slate-100 p-2">Pengumuman</li>
              </ul>
            </div>
          </div>
          <div class="Sapras relative inline-block group cursor-pointer">
            <div class="OnHover group flex items-center">
              <p title="Sarana dan Prasana" class="">Sapras</p>
              <Icon name="material-symbols:keyboard-arrow-down-rounded" class="group-hover:rotate-180" />
            </div>
            <div
              class="ListHover absolute left-0 z-10 hidden origin-top-right bg-white shadow-md w-[150px] divide-y divide-gray-100 group-hover:block group-hover:transition-all group-hover:ease-in-out group-hover:duration-300">
              <ul>
                <li class="hover:bg-slate-100 p-2">Tanah</li>
                <li class="hover:bg-slate-100 p-2">Ruang Kelas</li>
                <li class="hover:bg-slate-100 p-2">Ruang Praktek Siswa</li>
                <li class="hover:bg-slate-100 p-2">Ruang Penunjang</li>
              </ul>
            </div>
          </div>
          <NuxtLink to="/">
            <p class="">Gallery</p>
          </NuxtLink>
        </div>
      </div>
    </header>
  </div>

  <!-- Navigation -->
</template>

<style scoped>
/* Menambahkan transisi atau menyesuaikan gaya dropdown jika diperlukan */
</style>
