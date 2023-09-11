<template>
  <div>
    <router-link v-for="item in items" :key="item.id" :to="item.slug">
      <h1 :class="[item.selected ? 'selected' : '']" @click="onClick(item)">
        {{ item.name }}
      </h1>
    </router-link>
  </div>
</template>
<script>
import sourceData from '../data.json';

export default {

  data() {
    return {
      items: sourceData.sidemenu,
    };
  },
  methods: {
    onClick(item) {
      this.items.forEach(item => {
        item.selected = false;
      });
      item.selected = true;
    },
  },
};
</script>
<style scoped>
div {
  margin-top: 5rem;
}
h1 {
  font-size: 2rem;
  margin: 1rem;
  color: #313131;
  height: 5rem;
  display: flex;
  align-items: center;
  padding: 1rem;
}
.selected {
  background-color: teal;
  color: white;
  border-radius: 5px;
  box-shadow: -2px 2px 5px 2px teal;
}
</style>
