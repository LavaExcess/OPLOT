<script setup>

import Header from "@/components/ui/structure/Header.vue";
import Hero from "@/components/ui/structure/Hero.vue";
import Stats from "@/components/ui/structure/Stats.vue";
import Reviews from "@/components/ui/structure/Reviews.vue";
import Services from "@/components/ui/structure/Services.vue";
import Feedback from "@/components/ui/structure/Feedback.vue";
import DarkMode from "@/components/ui/structure/DarkMode.vue";
</script>

<template>
    <DarkMode />
    <header>
        <Header />
    </header>
    <main>
        <Hero />
    </main>
    <section>
        <Services />
    </section>
    <section>
        <Stats />
    </section>
    <section>
        <Reviews />
    </section>


    <section>
        <Feedback />
    </section>
</template>

<style scoped>
.logo {
    height: 6em;
    padding: 1.5em;
    will-change: filter;
    transition: filter 300ms;
}

.logo:hover {
    filter: drop-shadow(0 0 2em #646cffaa);
}

.logo.vue:hover {
    filter: drop-shadow(0 0 2em #42b883aa);
}
</style>
