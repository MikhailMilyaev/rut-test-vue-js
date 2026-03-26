<script setup>

</script>

<template>
    <div class="content-head">
        <button class="content-head__back">
            <svg width="24" height="24" viewBox="0 0 24 24" fill="none" xmlns="http://www.w3.org/2000/svg">
                <path fill-rule="evenodd" clip-rule="evenodd" d="M15.7071 5.29289C16.0976 5.68342 16.0976 6.31658 15.7071 6.70711L10.4142 12L15.7071 17.2929C16.0976 17.6834 16.0976 18.3166 15.7071 18.7071C15.3166 19.0976 14.6834 19.0976 14.2929 18.7071L8.29289 12.7071C7.90237 12.3166 7.90237 11.6834 8.29289 11.2929L14.2929 5.29289C14.6834 4.90237 15.3166 4.90237 15.7071 5.29289Z" fill="#E3E3E3"/>
            </svg>
            <span class="content-head__back-text">Назад</span>
        </button>

        <div class="content-head__header">
            <h1 class="content-head__title">Строительство</h1>
            <button class="content-head__date">
                <svg width="24" height="24" viewBox="0 0 24 24" fill="none" xmlns="http://www.w3.org/2000/svg">
                    <path d="M20 11H4V20C4 20.5523 4.44771 21 5 21H19C19.5523 21 20 20.5523 20 20V11ZM15 6V5H9V6C9 6.55228 8.55228 7 8 7C7.44772 7 7 6.55228 7 6V5H5C4.44772 5 4 5.44772 4 6V9H20V6C20 5.44771 19.5523 5 19 5H17V6C17 6.55228 16.5523 7 16 7C15.4477 7 15 6.55228 15 6ZM22 20C22 21.6569 20.6569 23 19 23H5C3.34315 23 2 21.6569 2 20V6C2 4.34315 3.34315 3 5 3H7V2C7 1.44772 7.44772 1 8 1C8.55228 1 9 1.44772 9 2V3H15V2C15 1.44772 15.4477 1 16 1C16.5523 1 17 1.44772 17 2V3H19C20.6569 3 22 4.34315 22 6V20Z" fill="#475057"/>
                </svg>
                <p class="content-head__date-text">27 мая 2025 г.</p>
                <svg width="24" height="24" viewBox="0 0 24 24" fill="none" xmlns="http://www.w3.org/2000/svg">
                    <path fill-rule="evenodd" clip-rule="evenodd" d="M5.29289 8.29289C5.68342 7.90237 6.31658 7.90237 6.70711 8.29289L12 13.5858L17.2929 8.29289C17.6834 7.90237 18.3166 7.90237 18.7071 8.29289C19.0976 8.68342 19.0976 9.31658 18.7071 9.70711L12.7071 15.7071C12.3166 16.0976 11.6834 16.0976 11.2929 15.7071L5.29289 9.70711C4.90237 9.31658 4.90237 8.68342 5.29289 8.29289Z" fill="white"/>
                </svg>
            </button>
        </div>

        <div class="content-head__tabs tabs">
            <button class="tabs__item">Вход в Санкт-Петербург</button>
            <button class="tabs__item tabs__item--active">Центральный участок</button>
            <button class="tabs__item">Вход в Москву</button>
        </div>
        
    </div>
</template>

<style scoped>
.content-head {
    display: flex;
    flex-direction: column;
    width: 100%;
}

.content-head__back {
    width: 83px;
    height: 48px;
    align-self: flex-start;

    display: flex;
    align-items: center;
    gap: 3px;
    background: none;
    border: none;
    font-size: 18px;
    font-weight: 600;
    color: var(--color-text-primary-inverse);
    cursor: pointer;
    margin-bottom: 8px;
}

.content-head__header {
    display: flex;
    justify-content: space-between;
    align-items: center;
    margin-bottom: 20px;
}

.content-head__title {
    font-size: 48px;
    font-weight: 600;
    line-height: 54px;
    color: var(--color-text-primary);
}

.content-head__date {
    height: 60px;
    display: flex;
    align-items: center;
    gap: 8px;
    background-color: var(--color-bg-secondary-2);
    border: none;
    padding: 3px 5px;
    border-radius: 2px;
    cursor: pointer;
    box-shadow: rgba(0, 0, 0, 0.05);
}

.content-head__date-text {
    color: var(--color-text-primary-inverse);
    font-size: 18px;
    line-height: 18px;
    font-weight: 600;
}

.tabs {
    display: flex;
    width: 100%;
    height: 48px; 
    justify-content: space-between;
    gap: 2px;
}

.tabs__item {
    flex: 1;
    display: flex;
    align-items: center;
    justify-content: center;
    border: none;
    background: none;
    border-radius: 2px;
    height: 48px;
    font-size: 18px;
    font-weight: 600;
    line-height: 20px;
    background-color: var(--color-bg-secondary);
    color: var(--color-text-primary);
    padding: 10px 4px;
    
    cursor: pointer;
    transition: all 0.3s ease;
    white-space: nowrap;
}

.tabs__item--active {
    color: var(--color-bg-primary);
    background-color: var(--color-text-primary-inverse);

}

.tabs__item:not(.tabs__item--active):hover {
    color: var(--color-text-primary);
    background-color: rgba(255, 255, 255, 0.05);
}

</style>