<template>
  <div class="dashboard_header d-flex flex-row justify-content-between p-5">
    <h1>Dashboard</h1>
    <div class="d-flex flex-row align-items-center">
      <form>
        <button class="h-100">
          <i class="fa-solid fa-magnifying-glass fs-3"></i>
        </button>
        <input class="h-100" type="text" />
      </form>
      <button><i class="fa-solid fa-bell fs-3"></i></button>
    </div>
  </div>
  <div class="d-flex flex-row justify-content-between">
      <div class="col-4">
        <canvas id="chart"></canvas>
        <DashboardChart :chart="chart" /> 
      </div>
    
      <div class="col-4">
        <BalanceDashboard />
        <div>
            <DashboardPlaning   />
        </div>
      </div>

    

  </div>



</template>



<script>
import BalanceDashboard from './BalanceDashboard.vue';
// import DashboardChart from '../components/DashboardChart.vue';
import DashboardPlaning from '../components/DashboardPlaning.vue'
export default {
  data(){
    return{
      canvas :document.getElementById("chart"),

    }
  },
    components:{
        BalanceDashboard,
        // DashboardChart,
        DashboardPlaning
    }

}
</script>
<style scoped>
form {
  display: flex;
  width: 10rem;
  margin: 0 5rem;
  height: 3rem;
  border-radius: 5px;
}
form > * {
  background: #e2e2e2;
  border: none;
}
i {
  background: none;
  color: #000;
}
button {
  background: #e2e2e2;
  border: none;
  height: 3rem;
  width: 3rem;
}
</style>
