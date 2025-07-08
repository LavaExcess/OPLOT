<template>
    <section class="stats">
        <div class="stats__container">
            <div class="stats__header">
                <h2 class="stats__title">Мы разводим — вы страдаете!</h2>
                <p class="stats__description">
                    С щенками редко гуляют, поэтому они вынуждены писать и какать прямо в квартире своей хозяйки. <br />
                    А еще им немножко скучно, поэтому они грызут гибкую подводку водопровода и воют в постоянно открытое
                    окно.
                </p>
            </div>
            <div class="stats__items">
                <div class="stats__item" v-for="(item, idx) in sItems" :key="idx">
                    <div class="stats__item-content">
                        <div class="stats__icon-wrapper">
                            <component :is="item.svg" class="stats__icon" />
                        </div>
                        <div class="stats__text-wrapper">
                            <h3 class="stats__number">{{ item.number }}</h3>
                            <p class="stats__text">{{ item.text }}</p>
                        </div>
                    </div>
                </div>
            </div>
        </div>
    </section>
</template>

<script setup>
import Sticker from "@/components/ui/svg/Sticker.vue"
import Sheet from "@/components/ui/svg/Sheet.vue"
import Pizza from "@/components/ui/svg/Pizza.vue"
import Human from "@/components/ui/svg/Human.vue"

const sItems = [
    { svg: Sticker, number: "3", text: "Затоплены нечистотами" },
    { svg: Sheet, number: "20+", text: "Страдают от страшной вони" },
    { svg: Pizza, number: "200+", text: "Страдают от ночного визга" },
    { svg: Human, number: "10%", text: "Квартиры теряют в цене *" },
]
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
    @apply w-full font-bold text-4xl text-center text-[color:var(--foreground)];
}

.stats__description {
    @apply w-full font-normal text-lg text-center text-[color:var(--foreground)] mt-2;
}

.stats__items {
    @apply flex flex-col lg:flex-row items-center justify-center w-full gap-6 h-auto;
}

.stats__item {
    @apply flex flex-col items-center p-4 gap-4 w-[90%] lg:w-[302px] h-[100px] bg-[color:var(--card)] border border-[color:var(--border)] rounded-none flex-1;
}

.stats__item-content {
    @apply flex flex-row items-center w-full gap-4 h-auto;
}

.stats__icon-wrapper {
    @apply flex-shrink-0 flex justify-center items-center w-12 h-12 bg-[color:var(--muted)];
}

.stats__text-wrapper {
    @apply flex flex-col items-start w-full overflow-hidden;
}

.stats__number {
    @apply w-full font-bold text-xl text-[color:var(--foreground)] truncate;
}

.stats__text {
    @apply w-full font-normal text-base text-[color:var(--muted-foreground)] line-clamp-2;
}
</style>
