<script setup>
import Header from "@/components/ui/structure/Header.vue";
import Hero from "@/components/ui/structure/Hero.vue";
import Stats from "@/components/ui/structure/Stats.vue";
import Reviews from "@/components/ui/structure/Reviews.vue";
import Services from "@/components/ui/structure/Services.vue";
import DarkMode from "@/components/ui/structure/DarkMode.vue";
import Footer from "@/components/ui/structure/Footer.vue";
</script>
<template>
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
    <footer>
        <Footer />
    </footer>
</template>

