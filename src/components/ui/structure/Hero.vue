<template>
    <section class="hero">
        <!-- SVG -->
        <div class="hero__SVG">
            <Hero />
        </div>
        <!-- TEXT -->
        <div class="hero__text">
            <div class="hero__intro">
                <div class="hero__heading-group">
                    <h1 class="hero__title">
                        Убийственная вонь
                    </h1>
                    <h2 class="hero__subtitle">
                        в доме Маринеско
                    </h2>
                </div>
                <p class="hero__description">
                    Эта история о том, как жительница Кронштадта занялась разведением щенков французского бульдога в
                    своей квартире, превращая жизнь всех соседей по подъезду в
                    <span class="hero__highlight">вонючий и визгливый ад!</span>
                </p>
            </div>
            <div class="hero__actions">
                <Button class="hero__button">
                    <span class="hero__button-text">
                        Text
                    </span>
                </Button>
            </div>
        </div>
    </section>
</template>

<script setup>
import Button from "@/components/ui/button/Button.vue";
import Hero from "@/components/ui/svg/Hero.vue";
</script>

<style scoped>
@import "tailwindcss";

.hero {
    @apply flex flex-col md:flex-row items-center px-4 md:px-20 py-12 md:py-[160px] gap-8 md:gap-20 w-full min-h-screen md:h-screen bg-[color:var(--background)] z-0;
}

.hero__SVG {
    @apply relative w-full md:w-[50%] h-auto pt-16 flex justify-center;
}

.hero__text {
    @apply flex flex-col items-start w-full md:w-[50%] h-auto py-0 md:py-8 gap-12 md:gap-16 flex-none;
}

.hero__intro {
    @apply flex flex-col items-start w-full gap-6 md:gap-12 h-auto md:h-[261px];
}

.hero__heading-group {
    @apply flex flex-col items-center w-full gap-1 md:gap-2 h-auto md:h-[113px];
}

.hero__title {
    @apply w-full font-bold text-4xl md:text-[2.5rem] text-[color:var(--foreground)] text-center md:text-left;
}

.hero__subtitle {
    @apply w-full font-bold text-2xl md:text-[2rem] text-[color:var(--foreground)] text-center md:text-left;
}

.hero__description {
    @apply w-full lg:w-[70%] font-normal text-base md:text-lg text-[color:var(--foreground)] text-center md:text-left;
}

.hero__highlight {
    @apply font-bold text-[color:var(--primary)];
}

.hero__actions {
    @apply flex flex-col md:flex-row justify-center md:justify-start items-center w-full md:w-[184px] gap-4 h-auto md:h-14 relative md:pt-2;
}

.hero__button {
    @apply flex justify-center items-center px-3 py-2 w-[133px] md:w-[184px] h-10 md:h-14 bg-[color:var(--primary)] border-2 border-[color:var(--primary)] cursor-pointer;
}

.hero__button-text {
    @apply px-2 md:px-4 font-medium text-sm tracking-[0.5px] text-[color:var(--primary-foreground)];
}
</style>
