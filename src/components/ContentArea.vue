<script setup>
import ContentHead from './ContentHead.vue';
import ContentLeft from './ContentLeft.vue';
import ContentRight from './ContentRight.vue';

</script>

<template>
  <div class="content-area">
    <ContentHead />

    <div class="content-area__grid">
        <ContentLeft class="content-area__left" />
        <ContentRight class="content-area__right" />
    </div>
  </div>
</template>

<style scoped>
.content-area {
  display: flex;
  flex-direction: column;
  gap: 40px;
  overflow-y: auto;
  padding: 20px 40px 40px 40px;
  height: 100%;
  width: 100%;
  background-color: var(--color-bg-primary);
}

.content-area__grid {
    display: grid;
    grid-template-columns: 540px 1fr; 
    gap: 40px;
    width: 100%;
    max-width: 1920px; 
    margin: 0 auto; 
}

.content-area__left {
    width: 540px;
    flex-shrink: 0;
}

.content-area__right {
    min-width: 0;
    width: 100%;
}
</style>