<template>
    <section class="flex flex-col justify-center items-center px-4 py-12 gap-12 w-full bg-white md:px-20">
        <div class="flex flex-col items-center w-full gap-2 max-w-4xl">
            <div class="w-full font-bold text-xl text-center tracking-widest uppercase text-blue-900">
                Переживаете за нас?
            </div>
            <h2 class="w-full font-bold text-3xl md:text-4xl text-center text-gray-900">
                Оставьте анонимный отзыв
            </h2>
        </div>
        <div class="flex flex-col items-center gap-4 w-full max-w-2xl">
            <div class="flex flex-col items-start gap-1 w-full">
                <label class="w-full font-normal text-sm text-gray-900">
                    Имя необязательно
                </label>
                <div class="flex flex-row items-center w-full h-12 px-4 gap-2 bg-gray-50 border-b border-gray-300">
                    <input type="text" class="w-full font-normal text-base text-gray-500 bg-transparent outline-none"
                        placeholder="Имярек">
                </div>
            </div>
            <div class="flex flex-col items-start gap-1 w-full">
                <label class="w-full font-normal text-sm text-gray-900">
                    Комментарий желателен
                </label>
                <div
                    class="flex flex-row items-start w-full min-h-24 px-4 py-3.5 gap-2 bg-gray-50 border-b border-gray-300">
                    <textarea class="w-full font-normal text-base text-gray-500 bg-transparent outline-none resize-none"
                        placeholder="Что я вам скажу!"></textarea>
                </div>
            </div>
            <div class="flex flex-row justify-center items-center w-full mt-4">
                <Button
                    class="flex justify-center items-center px-6 py-3 w-full md:w-auto min-w-[250px] h-12 bg-blue-600 border-2 border-blue-600 cursor-pointer hover:bg-blue-700 transition-colors">
                    <span class="font-medium text-sm text-white">
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