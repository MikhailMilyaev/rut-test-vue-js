<script setup>
import { ref } from 'vue';

const slides = ref([
  { id: 1, title: '6 этап', url: 'https://images.unsplash.com/photo-1504307651254-35680f356dfd?auto=format&fit=crop&w=800&q=80' },
  { id: 2, title: '7 этап', url: 'https://images.unsplash.com/photo-1581094794329-c8112a89af12?auto=format&fit=crop&w=800&q=80' },
  { id: 3, title: '8 этап', url: 'https://images.unsplash.com/photo-1486406146926-c627a92ad1ab?auto=format&fit=crop&w=800&q=80' }
]);

const currentIndex = ref(0)

const nextSlide = () => {
    if (currentIndex.value < slides.value.length - 1) {
        currentIndex.value++
    }
}

const prevSlide = () => {
    if (currentIndex.value > 0) {
        currentIndex.value--
    }
};
</script>

<template>
  <div class="left-side">
    <div class="left-side__common-state common-state">
        <div class="common-state__construction">
            <div class="construction__header">
                <h2 class="construction__header-text">Общий статус по этапам</h2>
            </div>
            
            <div class="construction__broadcast broadcast">
                <img :src="slides[currentIndex].url" alt="картинка" class="broadcast__image"> 
            </div>

            <div class="construction__arrows arrows">
                <button @click="prevSlide" class="arrows__btn" :disabled="currentIndex === 0">
                    <svg width="8" height="14" viewBox="0 0 8 14" fill="none" xmlns="http://www.w3.org/2000/svg">
                        <path fill-rule="evenodd" clip-rule="evenodd" d="M7.70711 0.292893C8.09763 0.683417 8.09763 1.31658 7.70711 1.70711L2.41421 7L7.70711 12.2929C8.09763 12.6834 8.09763 13.3166 7.70711 13.7071C7.31658 14.0976 6.68342 14.0976 6.29289 13.7071L0.292893 7.70711C-0.0976311 7.31658 -0.0976311 6.68342 0.292893 6.29289L6.29289 0.292893C6.68342 -0.0976311 7.31658 -0.0976311 7.70711 0.292893Z" fill="#E3E3E3"/>
                    </svg>
                </button>
                <span class="arrows__text">{{ slides[currentIndex].title }}</span>
                <button @click="nextSlide" class="arrows__btn" :disabled="currentIndex === slides.length - 1">
                    <svg width="24" height="24" viewBox="0 0 24 24" fill="none" xmlns="http://www.w3.org/2000/svg">
                        <path fill-rule="evenodd" clip-rule="evenodd" d="M8.75628 5.29289C9.09799 4.90237 9.65201 4.90237 9.99372 5.29289L15.2437 11.2929C15.5854 11.6834 15.5854 12.3166 15.2437 12.7071L9.99372 18.7071C9.65201 19.0976 9.09799 19.0976 8.75628 18.7071C8.41457 18.3166 8.41457 17.6834 8.75628 17.2929L13.3876 12L8.75628 6.70711C8.41457 6.31658 8.41457 5.68342 8.75628 5.29289Z" fill="#E3E3E3"/>
                    </svg>
                </button>
            </div>
        </div>

        <div class="common-state__content">
            <div class="stats-block">
                <h4 class="stats-title">На строительных объектах задействовано:</h4>
                <div class="stats-row">
                    <div class="stat-col">
                        <div class="stat-value ">117</div>
                        <div class="stat-sub">из н/д</div>
                        <div class="stat-label">техники</div>
                    </div>
                    <div class="stat-col">
                        <div class="stat-value">402</div>
                        <div class="stat-sub">из н/д</div>
                        <div class="stat-label">человек</div>
                    </div>
                </div>
            </div>
            
            <div class="stats-separator"></div>

            <div class="stats-block">
                <h4 class="stats-title">Развернуты работы :</h4>
                <div class="stats-row right-row">
                    <div class="stat-col">
                        <div class="stat-value text-white">2</div>
                        <div class="stat-sub">из 9</div>
                        <div class="stat-label">этапов</div>
                    </div>
                    
                    <div class="stat-chart">
                        <svg class="stat-chart__layer stat-chart__ring" width="100" height="100" viewBox="0 0 100 100" fill="none" xmlns="http://www.w3.org/2000/svg">
                            <path d="M100 50C100 77.6142 77.6142 100 50 100C22.3858 100 0 77.6142 0 50C0 22.3858 22.3858 0 50 0C77.6142 0 100 22.3858 100 50ZM10 50C10 72.0914 27.9086 90 50 90C72.0914 90 90 72.0914 90 50C90 27.9086 72.0914 10 50 10C27.9086 10 10 27.9086 10 50Z" fill="#414247"/>
                        </svg>

                        <svg class="stat-chart__layer stat-chart__line" width="1" height="10" viewBox="0 0 1 10" fill="none" xmlns="http://www.w3.org/2000/svg">
                            <path d="M0.94244 10.0071C0.628281 10.0071 0.314125 10.0041 1.52588e-05 9.9982L0.188503 -2.28882e-05C0.439789 0.00471497 0.691113 0.00708008 0.942444 0.00708008L0.94244 10.0071Z" fill="#FF4D4D"/>
                        </svg>

                        <svg class="stat-chart__layer stat-chart__dot" width="5" height="5" viewBox="0 0 5 5" fill="none" xmlns="http://www.w3.org/2000/svg">
                            <path d="M4.40143 4.89929C2.93077 4.89929 1.46129 4.81611 2.67029e-05 4.65013L0.528198 3.05176e-05C1.81411 0.146088 3.10725 0.219292 4.40143 0.219292V4.89929Z" fill="#B8C0CC"/>
                        </svg>

                        <div class="stat-chart__info">
                            <span class="stat-chart__text-red">0,3%</span>
                            <span class="stat-chart__text-grey">1,8%</span>
                        </div>
                    </div>
                </div>
            </div>

        </div>

    </div>

    <div class="left-side__text-shape text-shape">
        <p class="text-shape__text">Ведется подготовка территории строительтва 7 этапа, в том числе в зоне строящихся путепроводов на ПК 5734 и ПК 6103, моста на ПК 6020</p>
        <p class="text-shape__text">Ведется подготовка территории строительтва 6 этапа, в том числе в зоне строящегося моста через р.Шоша на ПК 5059 и ПК 5335</p>
    </div>

    <div class="use-of-funds">
    <div class="construction__header">
        <h2 class="construction__header-text">Использование средств</h2>
    </div>

    <div class="use-of-funds__content">
        <div class="use-of-funds__info">
            <span class="use-of-funds__label">13,8 использовано</span>
        </div>

        <div class="progress-bar">
            <div class="progress-bar__fill" style="width: 7.9%"></div>
            
            <span class="progress-bar__percent">7,9%</span>
        </div>

        <p class="use-of-funds__subtext">175,1 из 1755,9 млрд привлечено</p>
    </div>
</div>

<div class="permission-block">
    <div class="construction__header">
        <h2 class="construction__header-text">Разрешение на строительство</h2>
    </div>

    <div class="permission-block__content">
        <div class="permission-block__info">
            <div class="permission-block__list">
                <div class="permission-block__item">
                    <svg width="16" height="16" viewBox="0 0 16 16" fill="none">
                        <circle cx="8" cy="8" r="8" fill="#2AB4AE"/>
                    </svg>
                    <span class="permission-block__label">0 разрешений на строительство</span>
                </div>
                <div class="permission-block__item">
                    <svg width="16" height="16" viewBox="0 0 16 16" fill="none">
                        <circle cx="8" cy="8" r="8" fill="#7B57E0"/>
                    </svg>
                    <span class="permission-block__label">0 положительных заключений ГГЭ</span>
                </div>
            </div>

            <button class="button-dark">
                <span class="button-dark__text">Подробнее</span> 
                <svg width="20" height="20" viewBox="0 0 20 20" fill="none">
                    <path d="M5.87521 14.1247L14.1248 5.87516M14.1248 5.87516H5.87521M14.1248 5.87516V14.1247" stroke="#E3E3E3" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"/>
                </svg>
            </button>
        </div>

        <div class="permission-block__chart-wrap">
            <div class="permission-block__chart chart-big">
                <svg class="chart-big__svg" width="163" height="163" viewBox="0 0 163 163" fill="none">
                    <path d="M163 81.5C163 126.511 126.511 163 81.5 163C36.4888 163 0 126.511 0 81.5C0 36.4888 36.4888 0 81.5 0C126.511 0 163 36.4888 163 81.5ZM16.3 81.5C16.3 117.509 45.491 146.7 81.5 146.7C117.509 146.7 146.7 117.509 146.7 81.5C146.7 45.491 117.509 16.3 81.5 16.3C45.491 16.3 16.3 45.491 16.3 81.5Z" fill="#414247"/>
                </svg>
                
                <div class="chart-big__data">
                    <div class="chart-big__value">0</div>
                    <div class="chart-big__label">из 11</div>
                </div>
            </div>
        </div>
    </div>
</div>
  </div>
</template>

<style scoped>
.left-side {
    display: flex;
    flex-direction: column;
    gap: 40px;
}

.common-state {
    display: flex;
    flex-direction: column;
    gap: 40px;
}

.common-state__construction {
    display: flex;
    flex-direction: column;
    gap: 20px;
}

.construction__header {
    background-color: var(--color-bg-grey);
    display: flex;
    align-items: center;
    justify-content: center;
    border-radius: 8px;
    height: 48px;
}

.construction__header-text {
    font-size: 20px;
    font-weight: 600;
    color: var(--color-text-primary-inverse);
}

.construction__broadcast {
    width: 100%;
    height: 272px;
    border-radius: 12px;
    overflow: hidden;
}

.broadcast__image {
    border-radius: 12px;
    width: 100%;
    height: 100%;
    object-fit: cover;
    display: block;
}

.construction__arrows {
    display: flex;
    justify-content: space-between;
    align-items: center;
}

.arrows__btn {
    width: 44px;
    height: 44px;
    border-radius: 50%;
    background-color: var(--color-bg-common-dark-light);
    display: flex;
    align-items: center;
    justify-content: center;
    border: none;
    cursor: pointer;
    transition: background 0.2s;
    padding: 0;
}

.arrows__btn:hover {
    background-color: rgba(85, 86, 91, 1);
}

.arrows__btn:disabled {
    opacity: 0.3;
    cursor: not-allowed;
}

.arrows__btn:disabled:hover {
    background-color: var(--color-bg-common-dark-light);
}

.arrows__text {
    font-size: 24px;
    font-weight: 600;
    color: var(--color-text-primary-inverse); 
    line-height: 24px;
}

.common-state__content {
    display: flex;
    justify-content: space-between;
    align-items: stretch;
    background-color: transparent;
}

.stats-block {
    display: flex;
    flex-direction: column;
    gap: 20px;
    flex: 1;
}

.stats-title {
    font-size: 20px;
    font-weight: 400;
    color: var(--color-text-primary-inverse);
    line-height: 20px;
    height: 56px;
}

.stats-row {
    display: flex;
    justify-content: space-between;
}

.right-row {
    justify-content: space-between;
    align-items: center;
}

.stat-col {
    display: flex;
    flex-direction: column;
    gap: 12px;
}

.stat-value {
    color: var(--сolor-text-succes);
    font-size: 32px;
    font-weight: 600;
    line-height: 38px;
}

.text-white {
    color: var(--color-text-primary-inverse);
}

.stat-sub {
    font-size: 24px;
    font-weight: 600;
    color: var(--color-text-inactive);
    line-height: 24px;
}

.stat-label {
    font-size: 24px;
    font-weight: 600;
    color: var(--color-text-primary-inverse);
    line-height: 24px;
}

.stats-separator {
    width: 2px;
    background-color: var(--color-bg-common-dark-light);
    margin: 0 20px;
    flex-shrink: 0;
}

.stat-chart {
    position: relative;
    width: 100px;
    height: 100px;
    flex-shrink: 0;
}

.stat-chart__layer {
    position: absolute;
}

.stat-chart__ring {
    top: 0;
    left: 0;
}

.stat-chart__line {
    bottom: 0;
    left: 50%;
    transform: translateX(-50%);
}

.stat-chart__dot {
    bottom: 10px;
    left: 50%;
    transform: translateX(-50%);
}

.stat-chart__info {
    position: absolute;
    top: 50%;
    left: 50%;
    transform: translate(-50%, -50%);
    display: flex;
    flex-direction: column;
    align-items: center;
    gap: 4px;
}

.stat-chart__text-red {
    font-size: 18px;
    font-weight: 600;
    color: var(--color-text-error);
    line-height: 18px;
}

.stat-chart__text-grey {
    font-size: 12px;
    font-weight: 600;
    color: var(--color-text-inactive);
    line-height: 14px;
}

.text-shape {
    background-color: var(--color-bg-secondary);
    border-radius: 16px;
    height: 234px;
}

.text-shape__text {
    line-height: 18px;
    font-size: 14px;
    font-weight: 400;
    color: var(--color-text-primary-inverse);
    padding: 20px;
}

.use-of-funds {
    display: flex;
    flex-direction: column;
    gap: 28px;
    border-radius: 12px;
}

.use-of-funds__content {
    display: flex;
    flex-direction: column;
}

.use-of-funds__info {
    display: flex;
    justify-content: space-between;
    align-items: flex-end;
    margin-bottom: 8px;
}

.use-of-funds__label {
    font-size: 18px;
    line-height: 20px;
    font-weight: 600;
    color: var(--сolor-text-succes);
}

.use-of-funds__percent {
    font-size: 16px;
    font-weight: 600;
    line-height: 20px;
    color: var(--color-text-primary-inverse);
}

.progress-bar {
    position: relative;
    width: 100%;
    height: 32px; 
    background-color: var(--color-bg-common-dark-light); 
    border-radius: 4px;
    overflow: hidden;
    margin-bottom: 8px;
    
    display: flex;
    align-items: center;
    justify-content: flex-end;
    padding-right: 8px;
}

.progress-bar__fill {
    position: absolute;
    top: 0;
    left: 0;
    height: 100%;
    background-color: var(--сolor-text-succes);
    z-index: 1;
}

.use-of-funds__subtext {
    font-size: 14px;
    font-weight: 600;
    line-height: 14px;
    color: var(--color-text-primary);
}

.permission-block {
    display: flex;
    flex-direction: column;
    gap: 20px;
}

.permission-block__content {
    display: flex;
    justify-content: flex-start;
    align-items: center;
    gap: 20px;
    width: 540px;
}

.permission-block__info {
    display: flex;
    flex-direction: column;
    width: 319px; 
    height: 163px;
    justify-content: space-between;
    flex-shrink: 0;
}

.permission-block__chart-wrap {
    width: 201px;
    display: flex;
    justify-content: center;
    align-items: center;
    padding: 0 19px;
    box-sizing: border-box;
    flex-shrink: 0;
}

.permission-block__list {
    display: flex;
    flex-direction: column;
    gap: 8px;
}

.permission-block__item {
    display: flex;
    align-items: center;
    gap: 8px;
}

.permission-block__label {
    font-size: 18px;
    font-weight: 400;
    color: var(--color-text-primary); 
    line-height: 20px;
}

.button-dark {
    width: 100%;
    height: 40px;
    display: flex;
    align-items: center;
    justify-content: center;
    gap: 8px;
    background-color: var(--color-bg-secondary-2);
    border: none;
    border-radius: 8px;
    cursor: pointer;
}

.button-dark__text {
    font-size: 14px;
    font-weight: 600;
    line-height: 14px;
    color: var(--color-text-primary);
}

.button-dark:hover { 
    background-color: rgba(255,255,255,0.1); 
}

.chart-big {
    position: relative;
    width: 163px;
    height: 163px;
    flex-shrink: 0;
}

.chart-big__svg {
    display: block;
}

.chart-big__data {
    position: absolute;
    top: 0;
    left: 0;
    width: 100%;
    height: 100%;
    display: flex;
    flex-direction: column;
    align-items: center;
    justify-content: center;
    pointer-events: none;
    text-align: center;
}

.chart-big__value {
    font-size: 40px;
    font-weight: 600;
    color: var(--сolor-text-succes);
    line-height: 46px; 
}

.chart-big__label {
    font-size: 24px;
    font-weight: 600;
    color: rgba(216, 216, 216, 1);
    line-height: 24px;
}
</style>