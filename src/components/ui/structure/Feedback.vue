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
    @apply flex flex-col justify-center items-center px-4 py-12 gap-12 w-full bg-[color:var(--card)] md:px-20;
}

.feedback__header {
    @apply flex flex-col items-center w-full gap-2 max-w-4xl;
}

.feedback__title {
    @apply w-full font-bold text-xl text-center tracking-widest uppercase text-[color:var(--primary)];
}

.feedback__subtitle {
    @apply w-full font-bold text-3xl md:text-4xl text-center text-[color:var(--foreground)];
}

.feedback__form {
    @apply flex flex-col items-center gap-4 w-full max-w-[700px];
}

.feedback__group {
    @apply flex flex-col items-start gap-1 w-full;
}

.feedback__label {
    @apply w-full font-normal text-sm text-[color:var(--foreground)];
}

.feedback__input-wrapper {
    @apply flex flex-row items-center w-full h-12 px-4 gap-2 bg-[color:var(--input)] border-b border-[color:var(--border)];
}

.feedback__input {
    @apply w-full font-normal text-base text-[color:var(--muted-foreground)] bg-transparent outline-none;
}

.feedback__textarea-wrapper {
    @apply flex flex-row items-start w-full min-h-24 px-4 py-3.5 gap-2 bg-[color:var(--input)] border-b border-[color:var(--border)];
}

.feedback__textarea {
    @apply w-full font-normal text-base text-[color:var(--muted-foreground)] bg-transparent outline-none resize-none;
}

.feedback__submit {
    @apply flex flex-row justify-center items-center w-full mt-4;
}

.feedback__button {
    @apply flex justify-center items-center px-6 py-3 w-full md:w-auto min-w-[250px] h-12 bg-[color:var(--primary)] border-2 border-[color:var(--primary)] cursor-pointer hover:bg-[color:var(--primary)]/90 transition-colors;
}

.feedback__button-text {
    @apply font-medium text-sm text-[color:var(--primary-foreground)];
}
</style>
