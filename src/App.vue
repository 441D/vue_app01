<script setup>
import Header from './components/Header.vue';
import Footer from './components/Footer.vue';
import MainTodo from './components/MainTodo.vue';
</script>

<template>
  <div class="wrap">
    <Header />
    <main class="main"><MainTodo /></main>
    <Footer />
  </div>
</template>

<style>
  @import 'assets/css/destyle.css';

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
