<!-- <template>{{ date.toString() }}</template> -->
<template>
  <main class="main">
    <Header />
    <section class="section">
      <Button type="main" />
      <div class="card-section">
        <Card type="front" number="01" name="dust-coat" />
        <Card type="fliped" number="02" name="караван верблюдов!" />
      </div>
    </section>
  </main>
</template>

<script setup>
// const date = new Date();
import Button from "./components/Button.vue";
import Header from "./components/Header.vue";
import Card from "./components/Card.vue";
</script>

<style scoped></style>
