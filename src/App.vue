<script setup>
import ContentArea from './components/ContentArea.vue';
import Header from './components/Header.vue';
import SideBar from './components/SideBar.vue';

</script>

<template>
  <div class="app-wrapper">
    <Header/>
    <div class="main-layout">
      <SideBar/>
      <ContentArea />
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
</style>
