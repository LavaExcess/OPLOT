<template>
    <section class="info">
        <div class="info__wrapper">
            <div class="info__main-card">
                <div class="info__card">
                    <div class="info__content">
                        <h3 class="info__card1-title">Один кирпич — три материала</h3>
                        <p class="info__card1-text">Колотый кирпич позволяет оформлять объекты недвижимости в едином
                            стиле, формируя единый ансамбль из вашего дома, ограды и окружающих дорожек.</p>
                    </div>
                </div>
            </div>
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
        </div>
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
    @apply box-border flex flex-col bg-[color:var(--card)] border-[color:var(--border)] px-4 py-12 gap-8 w-full mx-auto;
}

.info__wrapper {
    @apply flex flex-col md:flex-row gap-8 w-full;
}

.info__main-card {
    @apply w-full md:w-1/3;
}

.info__grid {
    @apply grid grid-cols-1 lg:grid-cols-3 gap-4 w-full md:w-full;
}

.info__card {
    @apply flex flex-col items-start bg-[color:var(--card)] border border-[color:var(--border)] w-full h-full;
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

.info__card1-title {
    @apply w-full font-bold text-4xl text-[color:var(--foreground)];
}

.info__card1-text {
    @apply w-full font-normal text-xl text-[color:var(--foreground)];
}


.info__actions {
    @apply px-4 pb-4;
}

.info__button {
    @apply flex py-2 pl-0 cursor-pointer;
}

.info__button-text {
    @apply font-medium text-sm flex tracking-wider text-[color:var(--primary)];
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