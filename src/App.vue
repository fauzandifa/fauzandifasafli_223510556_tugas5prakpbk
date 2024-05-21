<template>
  <q-layout view="hHh lpr fFf" class="poppins-font">
    <q-header elevated class="bg-transparent text-black">
      <q-toolbar>
        <q-btn dense flat round icon="menu" @click="toggleLeftDrawer" />
        <q-toolbar-title>
          <q-avatar>
            <img src="https://cdn.quasar.dev/logo-v2/svg/logo-mono-black.svg">
          </q-avatar>
          Shiroloka
        </q-toolbar-title>
      </q-toolbar>
    </q-header>

     <q-drawer show-if-above v-model="leftDrawerOpen" side="left" bordered>
      <q-list>
        <!-- Profil Pengguna -->
        <q-item bordered class="bg-grey">
          <q-item-section avatar >
            <q-avatar>
              <img src="https://i.pinimg.com/564x/be/38/3b/be383bedd646e4dd8a8e7c0cc304f9e9.jpg"> <!-- Gambar profil pengguna -->
            </q-avatar>
          </q-item-section >
          <q-item-section>
            <q-item-label lines="1">tohru</q-item-label> <!-- Nama pengguna -->
          </q-item-section>
        </q-item>

        <!-- Pilihan Menu -->
        <q-item clickable v-ripple >
          <q-item-section>profil saya</q-item-section>
        </q-item>
        <q-item clickable v-ripple>
          <q-item-section>wallet</q-item-section>
        </q-item>
        <q-item clickable v-ripple>
          <q-item-section>history</q-item-section>
        </q-item>
      </q-list>
    </q-drawer>

    <q-page-container>
  <h4>selamat datang di shiroloka,temukan penawaran tiket terbaik dan raih pengalaman liburan terbaikmu</h4>
  <!-- carousel -->
  <h6>ini beberapa tmpt yg kami rekomendasikan</h6>
  <q-carousel
    v-model="slide"
    swipeable
    animated
    control-color="white"
    navigation
    arrows
  >
    <q-carousel-slide name="style" class="column no-wrap flex-center">
      <q-img src="https://i.pinimg.com/736x/ed/b1/ab/edb1ab81c4dfdda99e9a70cbed522352.jpg" container-class="carousel-image" />
      <div class="q-mt-md text-center">
        {{ lorem }}
      </div>
    </q-carousel-slide>
    
    <q-carousel-slide name="tv" class="column no-wrap flex-center">
      <q-img src="https://i.pinimg.com/564x/a5/fb/76/a5fb76befb8f53db9b08fbbe3feef131.jpg" container-class="carousel-image" />
      <div class="q-mt-md text-center">
        {{ lorem }}
      </div>
    </q-carousel-slide>

    <q-carousel-slide name="layers" class="column no-wrap flex-center">
      <q-img src="https://i.pinimg.com/564x/69/3d/15/693d15aa8436bf68aaab78c291a98c0d.jpg" container-class="carousel-image" />
      <div class="q-mt-md text-center">
        {{ lorem }}
      </div>
    </q-carousel-slide>
  </q-carousel>
  <!-- card -->
<div class="card-container">
    <!-- First card -->
    <q-card class="my-card" flat bordered>
      <q-card-section>
      
      <div class="text-h5 q-mt-sm q-mb-xs">priority member</div>
      <div class="text-caption text-grey">
        Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua.
      </div>
    </q-card-section>
    </q-card>

    <!-- Second card -->
    <q-card class="my-card" flat bordered>
      <q-card-section>
      
      <div class="text-h5 q-mt-sm q-mb-xs">newbie member</div>
      <div class="text-caption text-grey">
        Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua.
      </div>
    </q-card-section>
    </q-card>

    <!-- Third card -->
    <q-card class="my-card" flat bordered>
      <q-card-section>
      <div class="text-h5 q-mt-sm q-mb-xs">common member</div>
      <div class="text-caption text-grey">
        Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua.
      </div>
    </q-card-section>
    </q-card>
    </div>
</q-page-container>


    <q-footer elevated class="bg-grey-8 text-white text-center">
      <q-toolbar>
        <q-toolbar-title>
          <p>fauzan difa safli</p>
          <p>223510556</p>
        </q-toolbar-title>
      </q-toolbar>
    </q-footer>
  </q-layout>
</template>

<script>
import { ref } from 'vue'

export default {
  setup () {
    const leftDrawerOpen = ref(false)
    const slide = ref('style') // Define reactive variable for carousel slide

    return {
      leftDrawerOpen,
      toggleLeftDrawer () {
        leftDrawerOpen.value = !leftDrawerOpen.value
      },
      slide // Return reactive variable for carousel slide
    }
  }
}
</script>

<style scoped>
/* Tambahkan aturan CSS untuk menggunakan font Poppins secara global */
.poppins-font {
  font-family: 'Poppins', sans-serif;
}
.carousel-image {
  object-fit: cover;
  width: 100%;
  height: 100%;
}
.card-container{
  display: flex;
  justify-content: center;

}
.my-card{
  width: 250px; /* Ubah lebar kartu */
  max-height: 400px; /* Atur tinggi maksimum kartu */
}
  </style>
