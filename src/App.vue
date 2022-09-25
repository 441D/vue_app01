<script setup>
import Header from './components/Header.vue';
import Footer from './components/Footer.vue';
import { useRouter } from 'vue-router';

const router = useRouter();
const goBlog = () => {
  router.push('/blog');
};
</script>

<template>
  <div class="wrap">
    <Header />
    <nav>
      <router-link to="/">Home</router-link>
      | <router-link to="/about">About</router-link>
      | <span @click="goBlog">Blog</span>
    </nav>
    <main class="main"><router-view /></main>
    <Footer />
  </div>
</template>

<style>
  @import 'assets/css/destyle.css';

  body {
    background-color: #333;
    color: #fff;
  }
  .wrap {
    display: flex;
    flex-direction: column;
    align-items: center;
    min-height: 100vh;
    width: 370px;
    margin: 0 auto;
    font-family: sans-serif;
  }

  .main {
    flex: 1;
    width: 100%;
  }
</style>
