<template>
    <section class="carousel">
        <Carousel :opts="carouselOptions" class="carousel__wrap" :plugins="[Autoplay({ delay: 5000 })]">
            <CarouselContent class="carousel__content">
                <CarouselItem v-for="testimonial in testimonials" :key="testimonial.id" class="carousel__item">
                    <div class="carousel__card">
                        <div class="carousel__avatar">
                            <Ava />
                        </div>
                        <p class="carousel__text">{{ testimonial.text }}</p>
                        <div class="carousel__info">
                            <h4 class="carousel__title">{{ testimonial.category }}</h4>
                            <p class="carousel__subtitle">{{ testimonial.subcategory }}</p>
                        </div>
                    </div>
                </CarouselItem>
            </CarouselContent>
            <CarouselPrevious class="carousel__nav carousel__nav--prev" />
            <CarouselNext class="carousel__nav carousel__nav--next" />
        </Carousel>
    </section>
</template>

<script setup lang="ts">
import {
    Carousel,
    CarouselContent,
    CarouselItem,
    CarouselNext,
    CarouselPrevious,
} from '@/components/ui/carousel'
import type { EmblaOptionsType } from 'embla-carousel'
import Autoplay from 'embla-carousel-autoplay'
import Ava from '@/components/ui/svg/Avatar.vue'
import testimonials from '@/assets/storage/testimonials.json'
const carouselOptions: EmblaOptionsType = {
    loop: true,
    align: 'center',
    slidesToScroll: 1,
    dragFree: false,
    containScroll: 'trimSnaps',
}
</script>

<style scoped>
@import "tailwindcss";

.carousel {
    @apply flex flex-col items-center p-12 md:p-20 gap-12 md:gap-16 w-full bg-[color:var(--muted)];
}

.carousel__wrap {
    @apply w-full md:max-w-[820px] max-w-[90%];
}

.carousel__content {
    @apply ml-0;
}

.carousel__item {
    @apply pl-0 basis-full;
}

.carousel__card {
    @apply flex flex-col items-center p-6 gap-4 w-full h-[327px] rounded-lg cursor-grab active:cursor-grabbing group-active:cursor-grabbing bg-[color:var(--card)];
}

.carousel__avatar {
    @apply flex justify-center items-center w-16 h-16 bg-[color:var(--muted)] rounded-full;
}

.carousel__text {
    @apply w-full font-normal text-base md:text-lg text-center text-[color:var(--foreground)] select-none;
}

.carousel__info {
    @apply flex flex-col items-center w-full gap-1;
}

.carousel__title {
    @apply w-full font-bold text-xl md:text-2xl text-center text-[color:var(--foreground)] select-none;
}

.carousel__subtitle {
    @apply w-full font-normal text-base md:text-lg text-center text-[color:var(--foreground)] select-none;
}

.carousel__nav {
    @apply md:flex size-10 absolute top-1/2 -translate-y-1/2 border-0 bg-[color:var(--muted)] hover:border-[color:var(--foreground)] active:scale-95 active:border-[color:var(--ring)] transition-all duration-200 cursor-grab active:cursor-grabbing focus-visible:outline-none focus-visible:ring-2 focus-visible:ring-[color:var(--ring)];
}

.carousel__nav--prev {
    @apply left-[-50px];
}

.carousel__nav--next {
    @apply right-[-50px];
}
</style>
