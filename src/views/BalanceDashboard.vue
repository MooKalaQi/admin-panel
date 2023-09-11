<template>
  <div class="row">
    <h4>
      Total Balance :
      <h2>{{ dashboardinfo.balance }}</h2>
    </h4>
  </div>
  <div class="row">
    <div class="col-4">
      <h6>
        Income :
        <h4>{{ dashboardinfo.income }}</h4>
      </h6>
    </div>
    <div class="col-4">
      <h6>
        Expenses :
        <h4>17300 </h4>
      </h6>
    </div>
    <div class="col-4">
      <h6>
        Creadit :
        <h4>{{ dashboardinfo.credit }}</h4>
      </h6>
    </div>
  </div>
</template>
<script>
import sourceData from '../data.json';
export default {
  name: "BalanceDashboard",
  data() {
    return{
      dashboardinfo: sourceData.dashboard[0]
    }
  },


};
</script>
