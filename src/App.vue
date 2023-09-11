<template>
  <div class="d-flex flex-row h-100">
    <div class="col-2">
      <Header></Header>

    </div>
    <div class="col-10">
      <router-view></router-view>
    </div>

  </div>
</template>
<script setup>
import Header from './components/Header.vue';
</script>


<style scoped></style>
