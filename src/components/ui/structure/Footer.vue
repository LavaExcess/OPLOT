<template>
    <footer class="footer">
        <div class="footer__top">
            <div class="footer__brand">
                <Brick class="footer__brand-icon" />
                Александровский Кирпич
            </div>
            <div class="footer__sub">
                <div class="footer__form">
                    <div class="footer__form-icon">
                        <Mail class="w-5 h-5" />
                    </div>
                    <input type="email" placeholder="Введите ваш email для подписки на нашу рассылку"
                        class="footer__input hidden lg:block" />
                    <input type="email" placeholder="Введите ваш email" class="footer__input lg:hidden" />
                </div>
                <Button class="footer__bottom ">
                    <span class="footer__button-text">
                        Подписаться
                    </span>
                </Button>
            </div>
        </div>
        <div class="footer__columns">
            <div class="footer__column" v-for="(column, index) in columns" :key="index">
                <h3 class="footer__column-title">{{ column.title }}</h3>
                <ul class="footer__column-list">
                    <li v-for="(item, i) in column.items" :key="i">
                        <a href="#" class="footer__column-link">{{ item }}</a>
                    </li>
                </ul>
                <template v-if="index === 3">
                    <div class="footer__apps">
                        <a href="#">
                            <AS />
                        </a>
                        <a href="#">
                            <GP />
                        </a>
                    </div>
                    <div class="footer__social">
                        <p class="footer__social-title">Join Us</p>
                        <div class="footer__social-icons">
                            <i class="fab fa-youtube"></i>
                            <i class="fab fa-twitter"></i>
                            <i class="fab fa-facebook"></i>
                            <i class="fab fa-instagram"></i>
                            <i class="fab fa-linkedin"></i>
                        </div>
                    </div>
                </template>
            </div>
        </div>
        <div class="footer__bottom">
            <p>Александровский Кирпич @2025. Все права защищены.</p>
            <div class="footer__bottom-links">
                <span>1</span>
                <span>2</span>
                <span>3</span>
            </div>
        </div>
    </footer>
</template>

<script setup>
import AS from "@/components/ui/svg/AppStore.vue"
import GP from "@/components/ui/svg/GooglePlay.vue"
import Brick from "@/components/ui/svg/Brick.vue"
import Mail from "@/components/ui/svg/Mail.vue"
import Button from "@/components/ui/button/Button.vue"
import columns from '@/assets/storage/footer.json'

</script>

<style scoped>
@import url("https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css");
@import "tailwindcss";

.footer {
    @apply bg-[#697077] text-[color:var(--accent)] px-10 py-12 w-full;
}

.footer__top {
    @apply flex flex-col sm:flex-row justify-between items-center gap-6 border-b border-white/30 pb-8;
}

.footer__brand {
    @apply text-lg font-semibold flex items-center gap-2;
}

.footer__brand-icon {
    @apply w-6 h-6;
}

.footer__sub {
    @apply sm:flex sm:flex-row flex flex-col w-full lg:max-w-[560px] max-w-[350px] gap-4 ;
}

.footer__form {
    @apply flex w-full bg-white;
}

.footer__form-icon {
    @apply px-3 pt-2  text-gray-500;
}

.footer__input {
    @apply text-[color:var(--foreground)] outline-none w-full h-8;
}


.footer__columns {
    @apply grid grid-cols-2 md:grid-cols-4 gap-8 mt-10 border-b border-white/30 pb-8;
}

.footer__column-title {
    @apply font-semibold mb-4;
}

.footer__column-list {
    @apply space-y-2 text-sm text-[color:var(--accent)];
}

.footer__column-link {
    @apply hover:underline;
}

.footer__apps {
    @apply mt-4 lg:flex gap-1;
}



.footer__social-title {
    @apply font-semibold mb-2;
}

.footer__social-icons {
    @apply flex gap-3 text-white/70;
}

.footer__bottom {
    @apply cursor-pointer;
}

.footer__button-text {
    @apply h-10 text-sm items-center flex ;
}

.footer__bottom-links {
    @apply flex gap-6 mt-2 md:mt-0;
}
</style>
