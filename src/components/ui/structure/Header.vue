<template>
    <header class="header" ref="headerRef">
        <div class="header__container">
            <NavigationMenu class="hidden md:block">
                <NavigationMenuList>
                    <NavigationMenuItem v-for="(item, index) in nav.menu" :key="index">
                        <NavigationMenuLink :href="item.url" :class="navigationMenuTriggerStyle()">
                            {{ item.label }}
                        </NavigationMenuLink>
                    </NavigationMenuItem>
                    <NavigationMenuItem>
                        <NavigationMenuTrigger>{{ nav.contacts }}</NavigationMenuTrigger>
                        <NavigationMenuContent class="bg-[color:var(--background)]">
                            <ul class="grid w-[400px] gap-3 p-4 md:w-[500px] md:grid-cols-2 lg:w-[600px]">
                                <li v-for="item in items" :key="item.urlId">
                                    <NavigationMenuLink as-child>
                                        <a :href="item.urlId"
                                            class="block select-none space-y-1 rounded-md p-3 leading-none no-underline outline-none transition-colors hover:bg-accent hover:text-accent-foreground focus:bg-accent focus:text-accent-foreground">
                                            <div class="text-sm font-medium leading-none">{{ item.title }}</div>
                                            <p class="line-clamp-2 text-sm leading-snug text-muted-foreground">
                                                {{ item.description }}
                                            </p>
                                        </a>
                                    </NavigationMenuLink>
                                </li>
                            </ul>
                        </NavigationMenuContent>
                    </NavigationMenuItem>
                </NavigationMenuList>
            </NavigationMenu>
            <div class="header__branding">
                <div class="header__logo">
                    <Brick />
                </div>
                <a href="#" class="header__link">Александровский Кирпич</a>
            </div>
            <div class="header__nav">
                <Button class="hero__button text-[color:var(--border2)] bg-[color:var(--background)]">
                    <span class="hero__button-text">{{ nav.buttons.login }}</span>
                </Button>
                <Button class="hero__button bg-[color:var(--border2)]">
                    <span class="hero__button-text">{{ nav.buttons.contact }}</span>
                </Button>
            </div>
            <div class="header__burger md:hidden" @click.stop="toggleMobileMenu" role="button"
                aria-label="Toggle mobile menu">
                <div class="header__burger-line" />
                <div class="header__burger-line" />
                <div class="header__burger-line" />
            </div>
        </div>
        <Transition name="slide-down">
            <NavigationMenu v-if="isMobileMenuOpen" class="md:hidden">
                <div class="header__mobile-menu" @click.stop>
                    <NavigationMenuList class="flex flex-col">
                        <NavigationMenuItem v-for="(item, index) in nav.menu" :key="index">
                            <NavigationMenuLink :href="item.url">
                                {{ item.label }}
                            </NavigationMenuLink>
                        </NavigationMenuItem>
                        <NavigationMenuItem>
                            <NavigationMenuTrigger>{{ nav.contacts }}</NavigationMenuTrigger>
                            <NavigationMenuContent class="bg-[color:var(--background)]">
                                <ul class="grid gap-3 p-2 grid-cols-1 flex w-[330px]">
                                    <li v-for="item in items" :key="item.urlId">
                                        <NavigationMenuLink as-child>
                                            <a :href="item.urlId"
                                                class="block select-none space-y-1 rounded-md p-3 leading-none no-underline outline-none transition-colors hover:bg-accent hover:text-accent-foreground focus:bg-accent focus:text-accent-foreground">
                                                <div class="text-sm font-medium leading-none">{{ item.title }}</div>
                                                <p class="line-clamp-2 text-sm leading-snug text-muted-foreground">
                                                    {{ item.description }}
                                                </p>
                                            </a>
                                        </NavigationMenuLink>
                                    </li>
                                </ul>
                            </NavigationMenuContent>
                        </NavigationMenuItem>
                        <div class="flex flex-col space-y-2 mt-4 px-2">
                            <Button
                                class="hero__button text-[color:var(--border2)] bg-[color:var(--background)] w-full">
                                <span class="hero__button-text">{{ nav.buttons.login }}</span>
                            </Button>
                            <Button class="hero__button bg-[color:var(--border2)] w-full">
                                <span class="hero__button-text">{{ nav.buttons.contact }}</span>
                            </Button>
                        </div>
                    </NavigationMenuList>
                </div>
            </NavigationMenu>
        </Transition>
    </header>
</template>

<script setup>
import Button from "@/components/ui/button/Button.vue";
import Brick from "@/components/ui/svg/Brick.vue";
import items from "@/assets/storage/items.json";
import nav from "@/assets/storage/header.json";

import {
    NavigationMenu,
    NavigationMenuContent,
    NavigationMenuItem,
    NavigationMenuLink,
    NavigationMenuList,
    NavigationMenuTrigger
} from "@/components/ui/navigation-menu";
import { navigationMenuTriggerStyle } from "@/components/ui/navigation-menu";

import { ref, onMounted, onBeforeUnmount } from "vue";

const isMobileMenuOpen = ref(false);
const headerRef = ref(null);

const toggleMobileMenu = () => {
    isMobileMenuOpen.value = !isMobileMenuOpen.value;
};

const closeMobileMenu = (event) => {
    if (isMobileMenuOpen.value && headerRef.value && !headerRef.value.contains(event.target)) {
        isMobileMenuOpen.value = false;
    }
};

onMounted(() => {
    document.addEventListener('click', closeMobileMenu);
});

onBeforeUnmount(() => {
    document.removeEventListener('click', closeMobileMenu);
});
</script>

<style scoped>
@import "tailwindcss";

.header {
    @apply w-full fixed top-0 left-0 z-50 bg-[color:var(--background)] h-[72px];
    box-shadow: 0 1px 2px 0 hsl(var(--shadow-color));
}

.header__container {
    @apply container mx-auto flex items-center justify-between h-full px-4 relative;
}

.header__branding {
    @apply flex items-center justify-center absolute left-1/2 transform -translate-x-1/2;
}

.header__logo {
    @apply flex-shrink-0 pt-1 w-14 h-auto;
}

.header__link {
    @apply ml-2 font-bold text-lg md:text-xl lg:text-2xl text-[color:var(--foreground)];
}

.header__nav {
    @apply hidden md:flex items-center space-x-6;
}

.hero__button {
    @apply flex justify-center items-center px-3 py-2 w-[133px] md:w-[188px] h-10 md:h-12 border-2 border-[color:var(--border2)] cursor-pointer;
}

.hero__button-text {
    @apply px-2 md:px-4 font-medium text-sm tracking-[0.5px];
}

.header__burger {
    @apply md:hidden flex flex-col space-y-1.5 w-6 cursor-pointer;
}

.header__burger-line {
    @apply w-full h-0.5 bg-gray-600;
}

.header__mobile-menu {
    @apply fixed top-[72px] left-0 right-0 w-full shadow-md py-2 px-4 bg-[color:var(--background)] z-40;
}
</style>