<template>
    <section class="feedback">
        <div class="feedback__header">
            <div class="feedback__title">
                Переживаете за нас?
            </div>
            <h2 class="feedback__subtitle">
                Оставьте анонимный отзыв
            </h2>
        </div>
        <div class="feedback__form">
            <div class="feedback__group">
                <label class="feedback__label">
                    Имя необязательно
                </label>
                <div class="feedback__input-wrapper">
                    <input type="text" class="feedback__input" placeholder="Имярек" />
                </div>
            </div>
            <div class="feedback__group">
                <label class="feedback__label">
                    Комментарий желателен
                </label>
                <div class="feedback__textarea-wrapper">
                    <textarea class="feedback__textarea" placeholder="Что я вам скажу!"></textarea>
                </div>
            </div>
            <div class="feedback__submit">
                <Button class="feedback__button">
                    <span class="feedback__button-text">
                        Всем сердцем с вами!
                    </span>
                </Button>
            </div>
        </div>
    </section>
</template>

<script setup>
import Button from "@/components/ui/button/Button.vue"
</script>



<style scoped>
@import "tailwindcss";




.feedback {
    @apply flex flex-col justify-center items-center px-4 py-12 gap-12 w-full bg-white md:px-20;
}

.feedback__header {
    @apply flex flex-col items-center w-full gap-2 max-w-4xl;
}

.feedback__title {
    @apply w-full font-bold text-xl text-center tracking-widest uppercase text-blue-900;
}

.feedback__subtitle {
    @apply w-full font-bold text-3xl md:text-4xl text-center text-gray-900;
}

.feedback__form {
    @apply flex flex-col items-center gap-4 w-full max-w-2xl;
}

.feedback__group {
    @apply flex flex-col items-start gap-1 w-full;
}

.feedback__label {
    @apply w-full font-normal text-sm text-gray-900;
}

.feedback__input-wrapper {
    @apply flex flex-row items-center w-full h-12 px-4 gap-2 bg-gray-50 border-b border-gray-300;
}

.feedback__input {
    @apply w-full font-normal text-base text-gray-500 bg-transparent outline-none;
}

.feedback__textarea-wrapper {
    @apply flex flex-row items-start w-full min-h-24 px-4 py-3.5 gap-2 bg-gray-50 border-b border-gray-300;
}

.feedback__textarea {
    @apply w-full font-normal text-base text-gray-500 bg-transparent outline-none resize-none;
}

.feedback__submit {
    @apply flex flex-row justify-center items-center w-full mt-4;
}

.feedback__button {
    @apply flex justify-center items-center px-6 py-3 w-full md:w-auto min-w-[250px] h-12 bg-blue-600 border-2 border-blue-600 cursor-pointer hover:bg-blue-700 transition-colors;
}

.feedback__button-text {
    @apply font-medium text-sm text-white;
}
</style>