<template>
    <section class="info">
        <!-- Текст -->
        <div class="info__header">
            <div class="info__title-wrapper">
                <div class="info__subtitle">Почему появилась эта страница?</div>
                <h2 class="info__title">
                    Местные власти не могут решить нашу проблему
                </h2>
            </div>
        </div>

        <!-- Контейнер карточек -->
        <div class="info__grid">
            <div v-for="(card, index) in cards" :key="index" class="info__card">
                <div class="info__image-placeholder"></div>
                <div class="info__content">
                    <h3 class="info__card-title">{{ card.title }}</h3>
                    <p class="info__card-text">{{ card.description }}</p>
                </div>
                <div class="info__actions">
                    <button @click="openModal(card)" class="info__button">
                        <span class="info__button-text">
                            Подробнее
                            <Move />
                        </span>
                    </button>
                </div>
            </div>
        </div>
        <!-- Кнопка -->
        <Button class="info__main-button">
            <span class="info__main-button-text">Text</span>
        </Button>

        
        <!-- Модалка -->
        <section class="cards">
            <div v-if="isModalOpen" class="info__modal-backdrop" @click.self="closeModal">
                <div class="info__modal-content">
                    <button class="info__modal-close" @click="closeModal">&times;</button>
                    <h3 class="info__modal-title">{{ selectedCard.title }}</h3>
                    <p class="info__modal-text">{{ selectedCard.fullDescription }}</p>
                </div>
            </div>
        </section>
    </section>
</template>

<script setup>

import Button from "@/components/ui/button/Button.vue"
import Move from "@/components/ui/svg/ArrowMove.vue"
import { ref, onMounted } from 'vue'
import services from '@/assets/storage/services.json'

const isModalOpen = ref(false)
const selectedCard = ref(null)
const cards = ref(services)

const openModal = (card) => {
    selectedCard.value = card
    isModalOpen.value = true
    document.body.style.overflow = 'hidden'
    window.history.pushState({}, '', `/${card.urlId}`)
}

const closeModal = () => {
    isModalOpen.value = false
    selectedCard.value = null
    document.body.style.overflow = 'auto'
    window.history.pushState({}, '', '/')
}

onMounted(() => {
    const urlId = window.location.pathname.slice(1)
    if (urlId) {
        const card = cards.value.find(c => c.urlId === urlId)
        if (card) {
            openModal(card)
        }
    }
})

const handleCardClick = (card) => {
    openModal(card)
}
</script>
<style scoped>
@import "tailwindcss";

.info {
    @apply box-border flex flex-col items-center bg-[color:var(--card)] border-[color:var(--border)] px-4 py-12 gap-8 lg:px-20 lg:py-20 lg:gap-16 w-full mx-auto;
}

.info__header {
    @apply flex flex-col items-start w-full gap-6 md:gap-12;
}

.info__title-wrapper {
    @apply flex flex-col items-center w-full gap-2;
}

.info__subtitle {
    @apply w-full font-bold text-xl text-center tracking-widest uppercase text-[color:var(--primary)];
}

.info__title {
    @apply w-full font-bold text-2xl text-center text-[color:var(--foreground)] md:text-4xl;
}

.info__grid {
    @apply grid grid-cols-2 gap-4 w-full h-full lg:grid-cols-4 md:gap-8 justify-items-center;
}

.info__card {
    @apply flex flex-col items-start bg-[color:var(--card)] border border-[color:var(--border)] w-full;
}

.info__image-placeholder {
    @apply flex justify-center items-center w-full h-[220px] bg-[color:var(--muted)];
}

.info__content {
    @apply flex flex-col items-start p-4 pt-6 pb-4 gap-4 w-full;
}

.info__card-title {
    @apply w-full font-bold text-xl text-[color:var(--foreground)];
}

.info__card-text {
    @apply w-full font-normal text-sm text-[color:var(--foreground)] md:text-base;
}

.info__actions {
    @apply px-4;
}

.info__button {
    @apply flex py-2 pl-0 cursor-pointer;
}

.info__button-text {
    @apply font-medium text-sm flex tracking-wider text-[color:var(--primary)];
}

.info__main-button {
    @apply flex justify-center items-center px-3 py-2 w-[20%] min-w-[150px] h-12 bg-[color:var(--primary)] border-2 border-[color:var(--primary)] cursor-pointer;
}

.info__main-button-text {
    @apply px-2 md:px-4 font-medium text-sm text-[color:var(--primary-foreground)];
}

/* Модалка */

.info__modal-backdrop {
    @apply fixed inset-0 bg-[color:var(--ring)]/90 flex justify-center items-center z-[1000];
}

.info__modal-content {
    @apply bg-[color:var(--card)] p-6 rounded-lg w-[85%] h-[85%] relative mx-4;
}

.info__modal-close {
    @apply absolute top-2 right-2 text-4xl cursor-pointer text-[color:var(--foreground)];
}

.info__modal-title {
    @apply font-bold text-xl mb-4 text-[color:var(--foreground)];
}

.info__modal-text {
    @apply font-normal text-base text-[color:var(--foreground)];
}
</style>
