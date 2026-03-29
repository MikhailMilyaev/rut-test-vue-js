<script setup>
import { ref } from 'vue';

const stages = ref([
  { id: 1, title: 'Обухово-II - Великий Новгород', num: 1, fact: 0, plan: 0, peopleFact: '0', peoplePlan: '0', techFact: '123', techPlan: '200', status: 'success' },
  { id: 2, title: 'Великий Новгород - Валдай', num: 2, fact: 0, plan: 0, peopleFact: '0', peoplePlan: '0', techFact: '123', techPlan: '200', status: 'success' },
  { id: 3, title: 'Валдай - Выползово', num: 3, fact: 0.5, plan: 0, peopleFact: '0', peoplePlan: '0', techFact: '123', techPlan: '200', status: 'success' },
  { id: 4, title: 'Выползово - Логовежь', num: 4, fact: 0.5, plan: 0, peopleFact: '0', peoplePlan: '0', techFact: '123', techPlan: '200', status: 'success' },
  { id: 5, title: 'Логовежь - Новая Тверь', num: 5, fact: 0.5, plan: 1.5, peopleFact: '0', peoplePlan: '0', techFact: '123', techPlan: '200', status: 'error' },
  { id: 6, title: 'Новая Тверь - Высоково', num: 6, fact: 1, plan: 6.5, peopleFact: '74', peoplePlan: 'н/д', techFact: '27', techPlan: 'н/д', highlightFact: true, status: 'error' },
  { id: 7, title: 'Высоково - Крюково (Алабушево)', num: 7, fact: 2, plan: 8.3, peopleFact: '328', peoplePlan: 'н/д', techFact: '90', techPlan: 'н/д', highlightFact: true, status: 'error' },
  { id: 8, title: 'ДЦУ', num: 8, fact: 0.5, plan: 0, peopleFact: '0', peoplePlan: '0', techFact: '0', techPlan: '0', status: 'success' },
  { id: 9, title: 'Основное депо ВСМ – Обухово', num: 9, fact: 0.5, plan: 0, peopleFact: '0', peoplePlan: '0', techFact: '0', techPlan: '0', status: 'success' },
]);
</script>

<template>
  <div class="right-side">
    <div class="data-table">
      
      <div class="data-table__header data-grid">
        <div class="grid-cell cell-header">Этап, процесс готовности</div>
        <div class="grid-cell cell-header border-left">Кол-во человек</div>
        <div class="grid-cell cell-header border-left">Кол-во техники</div>
      </div>

      <div class="data-table__body">
        <div 
          v-for="stage in stages" 
          :key="stage.id" 
          class="data-grid data-row"
        >
          <div class="grid-cell cell-left stage-col">
            <h3 class="stage-col__title">{{ stage.title }}</h3>
            
            <div class="stage-col__content">
              <div class="stage-col__number">{{ stage.num }}</div>
              
              <div class="bars-wrap">
                <div class="progress-line fact-line">
                  <div class="progress-line__track">
                    <div :class="['status-marker', stage.status === 'error' ? 'marker-error' : 'marker-success']"></div>
                    <div :class="['progress-line__fill', stage.status === 'error' ? 'fill-error' : 'fill-success']" :style="{ width: stage.fact + '%' }"></div>
                    <div class="progress-line__value">{{ stage.fact }}%</div>
                  </div>
                  <div class="progress-line__label">Факт</div>
                </div>

                <div class="progress-line plan-line">
                  <div class="progress-line__track">
                    <div class="status-marker marker-plan"></div>
                    <div class="progress-line__fill fill-plan" :style="{ width: stage.plan + '%' }"></div>
                    <div class="progress-line__value">{{ stage.plan }}%</div>
                  </div>
                  <div class="progress-line__label">План</div>
                </div>
              </div>
            </div>
          </div>

          <div class="grid-cell cell-center border-left stats-col">
            <span :class="['stats-value', { 'text-teal': stage.highlightFact }]">{{ stage.peopleFact }}</span>
            <span class="stats-divider">/</span>
            <span class="stats-plan">{{ stage.peoplePlan }}</span>
          </div>

          <div class="grid-cell cell-center border-left stats-col">
            <span :class="['stats-value', { 'text-teal': stage.highlightFact }]">{{ stage.techFact }}</span>
            <span class="stats-divider">/</span>
            <span class="stats-plan">{{ stage.techPlan }}</span>
          </div>
        </div>
      </div>

    </div>

    <button class="button-dark button-stretched">
      <span class="button-dark__text">Подробнее</span> 
      <svg width="20" height="20" viewBox="0 0 20 20" fill="none" xmlns="http://www.w3.org/2000/svg">
          <path d="M5.87521 14.1247L14.1248 5.87516M14.1248 5.87516H5.87521M14.1248 5.87516V14.1247" stroke="#E3E3E3" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"/>
      </svg>
    </button>
  </div>
</template>

<style scoped>
.right-side {
  display: flex;
  flex-direction: column;
  height: 100%;
  width: 100%;
}

.data-table {
  display: flex;
  flex-direction: column;
  width: 100%;
  flex-grow: 1;
  margin-bottom: 20px;
}

.data-grid {
  display: grid;
  grid-template-columns: minmax(0, 1fr) 160px 160px; 
  width: 100%;
  gap: 0;
}

.grid-cell {
  padding: 16px 16px 16px 0;
  display: flex;
}

.data-row:first-child .grid-cell {
  padding-top: 36px;
}

.cell-header {
  height: 48px;
  background-color: var(--color-bg-grey);
  font-size: 20px;
  font-weight: 600;
  color: var(--color-text-primary-inverse);
  padding: 0 16px;
  display: flex;
  align-items: center;
  justify-content: center;
  text-align: center;
}

.data-table__header .cell-header:first-child {
  border-radius: 8px 0 0 8px;
}

.cell-left {
  justify-content: flex-start;
  flex-direction: column;
}

.cell-center {
  align-items: center;
  justify-content: center;
}

.border-left {
  border-left: 1px solid var(--color-bg-common-dark-light);
}

.stage-col {
  gap: 12px;
}

.stage-col__title {
  font-size: 18px;
  font-weight: 400;
  color: var(--color-text-primary-inverse);
  line-height: 18px;
}

.stage-col__content {
  display: flex;
  align-items: center;
  gap: 20px;
  width: 100%;
}

.stage-col__number {
  width: 76px;
  height: 76px;
  background-color: var(--color-bg-secondary);
  border-radius: 12px;
  display: flex;
  align-items: center;
  justify-content: center;
  font-size: 20px;
  line-height: 32px;
  font-weight: 600;
  color: var(--color-text-primary-inverse);
  flex-shrink: 0;
}

.bars-wrap {
  display: flex;
  flex-direction: column;
  gap: 8px;
  flex-grow: 1;
  min-width: 0;
}

.progress-line {
  display: flex;
  align-items: center;
  gap: 8px;
  width: 100%;
}

.progress-line__track {
  flex-grow: 1;
  background-color: var(--color-bg-common-dark-light);
  position: relative;
  overflow: hidden;
  display: flex;
  align-items: center;
  justify-content: flex-end;
}

.fact-line .progress-line__track { 
    height: 40px; 
}
.plan-line .progress-line__track { 
    height: 28px; 
}

.progress-line__fill {
  position: absolute;
  top: 0;
  left: 0;
  height: 100%;
}

.fill-success { 
    background-color: var(--сolor-text-succes); 
}

.fill-error { 
    background-color: var(--color-text-error); 
}

.fill-plan { 
    background-color: var(--color-text-inactive); 
}

.progress-line__value {
  position: relative;
  z-index: 3;
  font-size: 18px;
  font-weight: 600;
  color: var(--color-text-primary-inverse);
  line-height: 20px;
  padding: 14px 8px 14px 0;
}

.status-marker {
  position: absolute;
  left: 0;
  top: 0;
  width: 4px;
  z-index: 4;
}

.marker-success { 
    background-color: var(--сolor-text-succes); 
}

.marker-error { 
    background-color: var(--color-text-error); 
}

.marker-plan { 
    background-color: var(--color-text-inactive); 
}

.fact-line .status-marker { 
    height: 40px; 
}

.plan-line .status-marker { 
    height: 28px; 
}

.progress-line__label {
  font-size: 14px;
  font-weight: 600;
  color: var(--color-text-primary-inverse);
  width: 40px;
  flex-shrink: 0;
}

.stats-col {
  padding: 40px 16px 16px 16px; 
  font-size: 32px;
  line-height: 24px;
  font-weight: 600;
  color: var(--color-text-inactive);
}

.data-row:first-child .stats-col {
  padding-top: 60px;
}

.text-teal {
  color: var(--сolor-text-succes);
}

.stats-divider {
  margin: 0 2px;
}

.button-dark {
  display: flex;
  align-items: center;
  justify-content: center;
  gap: 8px;
  background-color: var(--color-bg-secondary-2);
  border: 1px solid transparent;
  border-radius: 8px;
  cursor: pointer;
  width: 100%;
  height: 48px;
  flex-shrink: 0;
  transition: background-color 0.2s;
}

.button-dark__text {
  font-size: 14px;
  line-height: 14px;
  font-weight: 600;
  color: var(--color-text-primary-inverse);
}

.button-dark:hover { 
  background-color: rgba(255,255,255,0.1); 
}
</style>