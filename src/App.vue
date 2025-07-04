<script setup lang="ts">

import Header from "@/components/ui/structure/Header.vue";
import Section1 from "@/components/ui/structure/Section1.vue";
import Section2 from "@/components/ui/structure/Section2.vue";
import Section3 from "@/components/ui/structure/Section3.vue";
import Section4 from "@/components/ui/structure/Section4.vue";
import Section5 from "@/components/ui/structure/Section5.vue";
</script>

<template>


    <Header />
    <Section1 />
    <Section2 />
    <Section3 />
    <Section4 />
    <Section5 />

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
