<script setup>
import { ref } from 'vue';

const slides = ref([
  { id: 1, title: '7 этап', url: 'https://images.unsplash.com/photo-1504307651254-35680f356dfd?w=600' },
  { id: 2, title: '8 этап', url: 'https://images.unsplash.com/photo-1504307651254-35680f356dfd?w=600' }
]);

const currentIndex = ref(0)

const nextSlide = () => {
    currentIndex.value = (currentIndex.value + 1) % slides.value.length
}

const prevSlide = () => {
  currentIndex.value = (currentIndex.value - 1 + slides.value.length) % slides.value.length;
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
                <button @click="prevSlide" class="arrows__btn">
                    <svg width="8" height="14" viewBox="0 0 8 14" fill="none" xmlns="http://www.w3.org/2000/svg">
                        <path fill-rule="evenodd" clip-rule="evenodd" d="M7.70711 0.292893C8.09763 0.683417 8.09763 1.31658 7.70711 1.70711L2.41421 7L7.70711 12.2929C8.09763 12.6834 8.09763 13.3166 7.70711 13.7071C7.31658 14.0976 6.68342 14.0976 6.29289 13.7071L0.292893 7.70711C-0.0976311 7.31658 -0.0976311 6.68342 0.292893 6.29289L6.29289 0.292893C6.68342 -0.0976311 7.31658 -0.0976311 7.70711 0.292893Z" fill="#E3E3E3"/>
                    </svg>
                </button>
                <span class="arrows__text">{{ slides[currentIndex].title }}</span>
                <button @click="nextSlide" class="arrows__btn">
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
                        <div class="stat-value text-teal">117</div>
                        <div class="stat-sub">из н/д</div>
                        <div class="stat-label">техники</div>
                    </div>
                    <div class="stat-col">
                        <div class="stat-value text-teal">402</div>
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
    font-size: 32px;
    font-weight: 600;
    line-height: 38px;
}

.text-teal { color: var(--сolor-text-succes) }
.text-white { color: var(--color-text-primary-inverse) }

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
</style>