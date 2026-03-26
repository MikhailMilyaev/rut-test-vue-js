<script setup>
import Header from './components/Header.vue';
import SideBar from './components/SideBar.vue';

</script>

<template>
  <div class="app-wrapper">
    <Header></Header>
    <div class="main-layout">
      <SideBar></SideBar>
      <main class="content-area">
        <h1>Area</h1>
      </main>
    </div>
  </div>
  
</template>

<style scoped>
.app-wrapper {
  display: flex;
  flex-direction: column;
  height: 100vh;
  overflow: hidden;
}

.main-layout {
  display: grid;
  grid-template-columns: 310px 1fr;
  flex: 1;
}

.content-area {
  overflow-y: auto;
  padding: 0 40px;
}
</style>
