<template>
  <div class="card" :class="{ active: isActive }">
    <h2>{{ name }}</h2>
    <p>{{ description }}</p>
    <li v-for="noded in hpcnodes" :key=noded.id>{{ noded }}</li>
    <button @click="$emit('toggle')">
      {{ isActive ? 'Stop' : 'Start' }}
    </button>
  </div>
</template>

<script>
/*const itemss = ['apple','orange'];*/
/*const itemss = [];*/
export default {
  name: 'AppCard',
  props: {
    name: String,
    description: String,
    hpcnodes: [],
    isActive: Boolean,
  },
};
</script>

<style scoped>
.card {
  /*background: rgba(255, 255, 255, 0.8);
  backdrop-filter: blur(10px);*/
  /* ... */
  background-color: #fff;
  border-radius: 8px;
  box-shadow: 0 4px 6px rgba(0, 0, 0, 0.1);
  padding: 20px;
  width: 300px;
  text-align: center;
  transition: all 0.3s ease;
}
.card.active {
  background-color: #e6f7ff;
  border: 2px solid #1890ff;
}
button {
  margin-top: 10px;
  padding: 8px 16px;
  background-color: #1890ff;
  color: #fff;
  border: none;
  border-radius: 4px;
  cursor: pointer;
}
button:hover {
  background-color: #40a9ff;
}
</style>
