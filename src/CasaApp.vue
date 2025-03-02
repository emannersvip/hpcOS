<template>
  <div id="app">
    <header class="header">
      <h1>HPCOS Dashboard</h1>
    </header>
    <main class="dashboard">
      <AppCard
        name="Login Nodes"
        description="A list of login nodes."
	nodes='Server1'
        :isActive="isAppActive"
        @toggle="toggleApp"
      />

      <AppCard
        name="Scheduler Nodes"
        description="A list of scheduler nodes."
	nodes='Scheduler1'
        :isActive="isAppActive"
        @toggle="toggleApp"
      />
      <AppCard
        name="Sample App"
        description="A simple app card."
	nodes=''
        :isActive="isAppActive"
        @toggle="toggleApp"
      />
      <p class="status" v-if="isAppActive">App is running!</p>
    </main>
  </div>
</template>

<script>
import AppCard from './components/AppCard.vue';

export default {
  name: 'App',
  components: {
    AppCard,
  },
  data() {
    return {
      isAppActive: false,
    };
  },
  methods: {
    toggleApp() {
      this.isAppActive = !this.isAppActive;
    },
  },
};
</script>

<style>
#app {
  font-family: Arial, sans-serif;
  min-height: 100vh;
  background-color: #f0f2f5;
  padding: 20px;
}
.header {
  text-align: center;
  padding: 20px;
  background-color: #fff;
  box-shadow: 0 2px 4px rgba(0, 0, 0, 0.1);
  margin-bottom: 20px;
}
.dashboard {
  display: flex;
  justify-content: center;
}
</style>
