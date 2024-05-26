<template>
  <div>
    <!-- Carousel Section -->
    <div class="q-pa-md">
      <q-carousel
        swipeable
        animated
        v-model="slide"
        thumbnails
        infinite
      >
        <q-carousel-slide :name="1" img-src="../src/assets/4.jpg" />
        <q-carousel-slide :name="2" img-src="../src/assets/5.jpg" />
        <q-carousel-slide :name="3" img-src="../src/assets/6.jpg" />
        <q-carousel-slide :name="4" img-src="../src/assets/7.jpg" />
      </q-carousel>
    </div>

    <div id="app">
      <!-- Navbar -->
      <nav class="navbar">
        <div class="container">
          <a href="#" class="navbar-brand">Tawica Shop</a>
          <ul class="navbar-nav">
            <li class="nav-item"><a href="#home" class="nav-link">Home</a></li>
            <li class="nav-item"><a href="#products" class="nav-link">Products</a></li>
            <li class="nav-item"><a href="#about-us" class="nav-link">About Us</a></li>
            <li class="nav-item"><a href="#contact" class="nav-link">Contact</a></li>
          </ul>
        </div>
      </nav>

      <!-- Sections -->
      <section id="home" class="hero">
        <div class="container">
          <h1>Welcome to Tawica Shop</h1>
          <p>Toko kami memiliki penawaran khusus bagi kamu yang berlangganan member di toko kami! Jangan sampai ketinggalan ya!^_^</p>
          <a href="#products" class="btn">Shop Now</a>
        </div>
      </section>

      <section id="products" class="featured-products">
        <div class="container">
          <h2>Produk Tawica</h2>
          <div class="product-grid">
            <div class="product-card" v-for="product in products" :key="product.id">
              <img :src="product.image" :alt="product.name" />
              <h3>{{ product.name }}</h3>
              <p>{{ product.price }}</p>
            </div>
          </div>
        </div>
      </section>

      <section id="about-us" class="about-us">
        <div class="container">
          <h2>About Us</h2>
          <p>Tawica shop korea version telah hadir di gangnam. Jangan lewatkan kesempatan kalian untuk hadir pada pembukaan eksklusif toko kami. 
            <br>Kami tunggu kedatangan kamu ya!
            Tawica hadir untuk ikut dalam semua moment di hidup kamu. Terima kasih sudah berbelanja di tawica!^_^
          </p>
        </div>
      </section>

      <section id="contact" class="contact">
        <div class="container">
          <h2>Contact Us</h2>
          <p>Jika terjadi kendala dalam pesanan atau barang yang kamu pesan,hubungi nomor dibawah ini ya +16022024</p>
        </div>
      </section>

      <div class="row no-wrap items-center">
          <div class="col text-h6 ellipsis">
            Tawica Shop
          </div>
        </div>

        <q-rating v-model="stars" :max="5" size="32px" />
      

      <q-card-section class="q-pt-none">
        <div class="text-subtitle1">
          $・Korea, Gangnam
        </div>
        <div class="text-caption text-grey">
          161 Apgujeong-ro Gangnam-gu Seoul
        </div>
      </q-card-section>

      <!-- Footer -->
      <footer>
        <div class="container">
          <p>&copy; 2024 ROSE MARRY WINTERS BF</p>
        </div>
      </footer>

      

    </div>
  </div>
</template>

<script>
import { ref } from 'vue';
import { Quasar, QCarousel, QCarouselSlide, QCarouselControl } from 'quasar';
import img1 from './assets/1.jpg';
import img2 from './assets/2.jpg';
import img3 from './assets/3.jpg';
import img4 from './assets/4.jpg';
import img5 from './assets/5.jpg';
import img6 from './assets/6.jpg';
import img7 from './assets/7.jpg';
import img8 from './assets/8.jpg';


export default {
  name: 'App',
  setup() {
    stars: ref(4)
    const slide = ref(1);
    const products = ref([
      { id: 1, name: 'Bata Vale', price: '$29.99', image: '../src/assets/1.jpg' },
      { id: 2, name: 'Blue Die', price: '$19.99', image: '../src/assets/2.jpg' },
      { id: 3, name: 'Black Mamba', price: '$39.99', image: '../src/assets/3.jpg' },
    ]);

    return {
      slide,
      products
    };
  },
};
</script>

<style>
@import 'quasar/dist/quasar.css';

body {
  font-family: Arial, sans-serif;
  margin: 0;
  padding: 0;
}

.navbar {
  background-color: #333;
  padding: 1rem 0;
}

.navbar .container {
  display: flex;
  justify-content: space-between;
  align-items: center;
}

.navbar-brand {
  color: #fff;
  text-decoration: none;
  font-size: 1.5rem;
}

.navbar-nav {
  list-style: none;
  display: flex;
  margin: 0;
  padding: 0;
}

.nav-item {
  margin-left: 1rem;
}

.nav-link {
  color: #fff;
  text-decoration: none;
}

.hero {
  background: url('../src/assets/8.jpg') no-repeat center center;
  background-size: cover;
  color: #020202;
  padding: 5rem 0;
  text-align: center;
}

.hero .container {
  max-width: 800px;
  margin: 0 auto;
}

.hero h1 {
  font-size: 3rem;
}

.hero p {
  font-size: 1.5rem;
}

.btn {
  background-color: #ff6b6b;
  color: #fff;
  padding: 1rem 2rem;
  text-decoration: none;
  border-radius: 5px;
  display: inline-block;
  margin-top: 1rem;
}

.featured-products {
  padding: 2rem 0;
  background-color: #f9f9f9;
}

.featured-products h2 {
  text-align: center;
  margin-bottom: 2rem;
}

.product-grid {
  display: flex;
  justify-content: center;
  gap: 2rem;
  flex-wrap: wrap;
}

.product-card {
  background-color: #fff;
  padding: 1rem;
  border: 1px solid #ddd;
  border-radius: 5px;
  text-align: center;
}

.product-card img {
  max-width: 100%;
  height: auto;
  border-bottom: 1px solid #ddd;
  padding-bottom: 1rem;
  margin-bottom: 1rem;
}

.about-us,
.contact {
  padding: 2rem 0;
  background-color: #fff;
  text-align: center;
}

.my-card {
  width: 50%;
  max-width: 100px;
}

footer {
  background-color: #333;
  color: #fff;
  text-align: center;
  padding: 1rem 0;
}
</style>
