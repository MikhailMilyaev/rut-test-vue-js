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
}

.content-area__grid {
    display: grid;
    grid-template-columns: 540px 1fr;
    gap: 40px;
    max-width: 1530px;
    width: 100%;
}

.content-area__left {
    width: 540px;
}

.content-area__right {
    min-width: 0;
}
</style>