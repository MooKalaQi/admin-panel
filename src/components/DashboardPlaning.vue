<template>
  <h3>Buy A Mac</h3>
  <input
    class="w-75 h-75"
    type="range"
    :max="this.mac.price"
    :value="this.mac.saved"
    disabled
  />

  <h3>Buy A Car</h3>
  <input
    class="w-75 h-75"
    type="range"
    :max="this.car.price"
    :value="this.car.saved"
    disabled
  />
</template>
<script>
import { compile, computed } from 'vue';
import sourceDara from '../data.json';
export default {
  data() {
    return {
      mac: sourceDara.dashboard[0].planings['buy a mac'],
      car: sourceDara.dashboard[0].planings['buy a car'],
    };
  },
  // computed:{
  //     planners(){

  //     }
  // }
};
</script>

<style scoped>


input::-webkit-slider-runnable-track{
background: teal;
border-radius: 5rem;
}
</style>