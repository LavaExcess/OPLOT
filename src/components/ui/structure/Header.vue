<template>
    <header class="header">
        <div class="header__container">
            <div class="header__logo-group">
                <div class="header__logo">
                    <Logo />
                </div>
                <div class="header__title-group">
                    <div class="header__title">Щенки бульдога</div>
                    <div class="header__subtitle">в Кронштадте</div>
                </div>
            </div>
            <nav class="header__nav">
                <a href="#" class="header__link">Документы</a>
                <a href="#" class="header__link">Новости</a>
                <a href="#" class="header__link">Контакты</a>
            </nav>
            <button class="header__burger" @click="OpenMenu = !OpenMenu">
                <span class="header__burger-line"></span>
                <span class="header__burger-line"></span>
                <span class="header__burger-line"></span>
            </button>
        </div>
        <div v-if="OpenMenu" class="header__mobile-menu">
            <a href="#" class="header__mobile-link">Документы</a>
            <a href="#" class="header__mobile-link">Новости</a>
            <a href="#" class="header__mobile-link">Контакты</a>
        </div>
    </header>
</template>

<script>
export default {
    data() {
        return {
            OpenMenu: false,
        }
    },
}
</script>

<script setup>
import Logo from "@/components/ui/svg/Logo.vue"
</script>

<style scoped>
@import "tailwindcss";

.header {
    @apply w-full h-[72px] bg-white shadow-sm fixed top-0 left-0 z-50;
}

.header__container {
    @apply container mx-auto flex items-center justify-between h-full px-4;
}

.header__logo-group {
    @apply flex items-start gap-1 h-[39px];
}

.header__logo {
    @apply flex-shrink-0 w-6 h-6 pt-2;
}

.header__title-group {
    @apply flex flex-col justify-between;
}

.header__title {
    @apply font-bold text-[24px] w-full text-gray-600;
}

.header__subtitle {
    @apply self-end text-[12px] text-gray-500 mt-[-2px];
}

.header__nav {
    @apply hidden md:flex items-center space-x-6;
}
.header__link,
.header__mobile-link {
    @apply text-gray-600 hover:text-gray-900;
}

.header__burger {
    @apply md:hidden flex flex-col space-y-1.5 w-6;
}

.header__burger-line {
    @apply w-full h-0.5 bg-gray-600;
}

.header__mobile-menu {
    @apply md:hidden absolute top-[72px] left-0 w-full bg-white shadow-md py-2 px-4;
}

.header__mobile-link {
    @apply block py-2;
}
</style>
