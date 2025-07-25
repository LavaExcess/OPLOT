<template>
    <section class="hero">
        <div class="hero__text">
            <div class="hero__intro">
                <div class="hero__heading-group">
                    <h1 class="hero__title">{{ heroText.title }}</h1>
                    <h2 class="hero__subtitle">{{ heroText.subtitle }}</h2>
                </div>
                <p class="hero__description">{{ heroText.description }}</p>
            </div>

            <div class="hero__actions">
                <Button class="hero__button">
                    <span class="hero__button-text">{{ heroText.buttons[0] }}</span>
                </Button>
                <Button class="hero__button bg-[color:var(--background)] text-[color:var(--border2)]">
                    <span class="hero__button-text">{{ heroText.buttons[1] }}</span>
                </Button>
            </div>
        </div>

        <div class="hero__SVG">
            <Hero />
        </div>
    </section>
</template>

<script setup>
import Button from "@/components/ui/button/Button.vue"
import Hero from "@/components/ui/svg/Hero.vue"
import heroText from "@/assets/storage/hero.json"
</script>

<style scoped>
@import "tailwindcss";

.hero {
    @apply flex flex-col md:flex-row items-center px-4 md:px-20 py-12 md:py-[160px] gap-8 md:gap-20 w-full min-h-screen bg-[color:var(--background)] z-0;
}

.hero__SVG {
    @apply relative w-full md:w-[45%] pt-8 md:pt-16 flex justify-center;
}

.hero__text {
    @apply flex flex-col items-start w-full md:w-[55%] gap-10 md:gap-16;
}

.hero__intro {
    @apply flex flex-col items-start w-full gap-6 md:gap-12 min-h-0;
    /* убрана фиксированная высота */
}

.hero__heading-group {
    @apply flex flex-col items-center md:items-start w-full gap-1 md:gap-2;
}

.hero__title {
    @apply w-full font-bold text-3xl sm:text-4xl md:text-6xl text-[color:var(--foreground)] text-center md:text-left leading-tight;
}

.hero__subtitle {
    @apply w-full font-bold text-2xl sm:text-3xl md:text-6xl text-[color:var(--foreground)] text-center md:text-left leading-tight;
}

.hero__description {
    @apply w-full font-normal text-base sm:text-lg text-[color:var(--foreground)] text-center md:text-left;
}

.hero__highlight {
    @apply font-bold text-[color:var(--primary)];
}

.hero__actions {
    @apply flex flex-col sm:flex-row justify-center md:justify-start items-center w-full gap-4 md:pt-2;
}

.hero__button {
    @apply flex justify-center items-center px-3 py-2 w-[140px] sm:w-[188px] h-10 sm:h-12 border-2 border-[color:var(--border2)] cursor-pointer;
}

.hero__button-text {
    @apply px-2 sm:px-4 font-medium text-sm tracking-[0.5px];
}
</style>
