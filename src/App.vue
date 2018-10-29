<template>
  <div id="app" class="container my-4 p-4">
    <img src="./assets/logo.png" class="float-right">
    <router-view></router-view>
  </div>
</template>

<script>
import IndexPage from './components/IndexPage.vue';
import AdminPage from './components/AdminPage.vue';
import VueRouter from 'vue-router'

const router = new VueRouter({
  routes: [
    { path: '/', component: IndexPage },
    { path: '/admin', component: AdminPage }
  ]
});

export default {
  router,
  name: 'app'
}
</script>

<style>
body {
  background-color: #333;
}

#app {
  background-color: #fff;
  border-radius: 8px;
}
</style>
