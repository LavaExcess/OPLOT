<template>
    <section class="stats">
        <div class="stats__container">
            <div class="stats__header">
                <h2 class="stats__title">ФАСАДЫ</h2>
                <p class="stats__description">
                    Александровский кирпич <br />
                    создан для вашего дома
                </p>
            </div>
            <div class="info-grid">
                <div v-for="(feature, index) in features" :key="index" class="feature-card">
                    <div class="feature-icon">
                        <component :is="getIconComponent(feature.icon)" />
                    </div>
                    <h3 class="feature-title">{{ feature.title }}</h3>
                    <p class="feature-text">{{ feature.text }}</p>
                </div>
            </div>
            <Button class="hero__button ">
                <span class="hero__button-text">
                    Предварительный расчёт
                </span>
            </Button>
        </div>
    </section>
</template>

<script setup>
import { ref } from 'vue'
import featuresData from '@/assets/storage/features.json'
import Suitcase from '@/components/ui/svg/Suitcase.vue'
import Bag from '@/components/ui/svg/Bag.vue'
import Pulse from '@/components/ui/svg/Pulse.vue'
import Car from '@/components/ui/svg/Car.vue'
import Button from "@/components/ui/button/Button.vue";
const features = ref(featuresData)

const iconComponents = {
    Suitcase,
    Bag,
    Pulse,
    Car
}

const getIconComponent = (iconName) => {
    return iconComponents[iconName] || null
}
</script>

<style scoped>
@import "tailwindcss";

.stats {
    @apply box-border flex flex-col items-center px-4 py-[40px] gap-12 w-full h-auto min-h-[300px] bg-[color:var(--card)] border-b border-[color:var(--border)] flex-none z-10;
}

.stats__container {
    @apply flex flex-col items-center w-full gap-12;
}

.stats__header {
    @apply flex flex-col items-center w-full gap-2 h-auto;
}

.stats__title {
    @apply w-full font-bold sm:text-4xl text-3xl text-center text-[color:var(--foreground)];
}

.stats__description {
    @apply w-full font-normal sm:text-2xl text-xl text-center text-[color:var(--foreground)] mt-2;
}


.info-grid {
    @apply grid grid-cols-1 md:grid-cols-2 gap-8 w-[90%];
}

.feature-card {
    @apply bg-[color:var(--card)] p-8 rounded-xl shadow-sm border border-[color:var(--border)] flex flex-col items-center text-center;
}


.feature-title {
    @apply text-xl font-semibold text-[color:var(--foreground)] mb-3;
}

.feature-text {
    @apply text-[color:var(--foreground)];
}


.hero__button {
    @apply flex justify-center items-center px-3 py-2 w-[200px] h-10 md:h-12 border-2 border-[color:var(--border2)] cursor-pointer;
}

.hero__button-text {
    @apply px-2 md:px-4 font-medium text-sm tracking-[0.5px];
}
</style>
