<template>
    <header class="header">
        <div class="header__container">
            <NavigationMenu>
                <NavigationMenuList>
                    <NavigationMenuItem >
                        <NavigationMenuLink href="/docs/introduction" :class="navigationMenuTriggerStyle()">
                            Преимущества
                        </NavigationMenuLink>
                        <NavigationMenuLink href="/docs/introduction" :class="navigationMenuTriggerStyle()">
                            Галерея работ
                        </NavigationMenuLink>
                    </NavigationMenuItem>
                    <NavigationMenuItem>
                        <NavigationMenuTrigger>Контакты</NavigationMenuTrigger>
                        <NavigationMenuContent class="bg-[color:var(--background)]">
                            <ul class="grid w-[400px] gap-3 p-4 md:w-[500px] md:grid-cols-2 lg:w-[600px] ">
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

            <div class="header__nav">
                <div class="header__logo">
                    <Poop />
                </div>
                <a href="#" class="header__link font-bold text-2xl">Александровский Кирпич</a>
            </div>

            <div class="header__nav">
                <Button class="hero__button text-[color:var(--border2)] bg-[color:var(--background)]">
                    <span class="hero__button-text">
                        Личный кабинет
                    </span>
                </Button>
                <Button class="hero__button bg-[color:var(--border2)]">
                    <span class="hero__button-text">
                        Связаться с нами
                    </span>
                </Button>
            </div>
        </div>
    </header>
</template>

<script>
import Button from "@/components/ui/button/Button.vue";
import items from '@/assets/storage/items.json'
import { navigationMenuTriggerStyle } from '@/components/ui/navigation-menu'
</script>

<script setup>
import testimonials from '@/assets/storage/testimonials.json'
import Logo from "@/components/ui/svg/Logo.vue"
import DarkMode from "@/components/ui/structure/DarkMode.vue";
import Poop from "@/components/ui/svg/PoopLogo.vue";
import {
    NavigationMenu,
    NavigationMenuContent,
    NavigationMenuIndicator,
    NavigationMenuItem,
    NavigationMenuLink,
    NavigationMenuList,
    NavigationMenuTrigger,
    NavigationMenuViewport,
} from '@/components/ui/navigation-menu'
</script>

<style scoped>
@import "tailwindcss";

.header {
    @apply w-full h-[72px] fixed top-0 left-0 z-50 bg-[color:var(--background)];
    box-shadow: 0 1px 2px 0 hsl(var(--shadow-color));
}

.header__container {
    @apply container mx-auto flex items-center justify-between h-full px-4;
}

.header__logo-group {
    @apply flex items-start gap-1 h-[39px] w-full;
}

.header__title-group {
    @apply flex flex-col justify-between;
}

.header__title {
    @apply font-bold text-[24px] w-full;
    color: hsl(var(--foreground));
}

.hero__button {
    @apply flex justify-center items-center px-3 py-2 w-[133px] md:w-[188px] h-10 md:h-12  border-2 border-[color:var(--border2)] cursor-pointer;
}

.hero__button-text {
    @apply px-2 md:px-4 font-medium text-sm tracking-[0.5px] ;
}

.header__nav {
    @apply hidden md:flex items-center space-x-6;
}

.header__nav-svg {
    @apply hidden md:flex items-center space-x-1;
}

.header__link,
.header__mobile-link {
    color: hsl(var(--foreground));
}

.header__logo {
    @apply flex-shrink-0 pt-1;
}

.header__burger {
    @apply md:hidden flex flex-col space-y-1.5 w-6;
}

.header__burger-line {
    @apply w-full h-0.5 bg-gray-600;
}

.header__mobile-menu {
    @apply md:hidden absolute top-[72px] left-0 w-full shadow-md py-2 px-4;
    background-color: hsl(var(--header-bg));
}

.header__mobile-link {
    @apply block py-2;
}
</style>
