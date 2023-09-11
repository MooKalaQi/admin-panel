<template>
  <nav class="d-flex flex-column align-items-center">
    <div>
      <router-link to="/">
        <div class="header_Logo d-flex flex-row p-5">
          <i class="fa-solid fa-crown fs-1"></i>
          <h1>DevBank</h1>
        </div>
      </router-link>
      <SideBar></SideBar>
    </div>
  </nav>
</template>
<script>
import SideBar from './SideBar.vue';
export default {
  components: {
    SideBar,
  },
};
</script>
<style scoped>
nav{
  height: 100%;
}
</style>
