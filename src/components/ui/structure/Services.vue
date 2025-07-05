<template>
    <section class="box-border flex flex-col items-center bg-white  border-gray-200 px-4 py-12 gap-8 
                 lg:px-20 lg:py-20 lg:gap-16 w-full   mx-auto">
        <!-- Текст  -->
        <div class="flex flex-col items-start w-full gap-6 md:gap-12 ">
            <div class="flex flex-col items-center w-full gap-2">
                <div class="w-full font-bold text-xl  text-center tracking-widest uppercase text-blue-900">
                    Почему появилась эта страница?
                </div>
                <h2 class="w-full font-bold text-2xl  text-center text-gray-900 md:text-4xl">
                    Местные власти не могут решить нашу проблему
                </h2>
            </div>
        </div>
        <!-- Контейнер -->
        <div class="grid grid-cols-2 gap-4 w-full h-full lg:grid-cols-4 md:gap-8 justify-items-center">
            <div v-for="(card, index) in cards" :key="index"
                class="flex flex-col items-start bg-white border border-gray-200 w-full   ">
                <!-- Заглушка, для картинок -->
                <div class="flex justify-center items-center w-full h-[220px] bg-gray-200"> </div>
                <!-- Контент -->
                <div class="flex flex-col items-start p-4 pt-6 pb-4 gap-4 w-full">
                    <div class="flex flex-col items-start gap-1 w-full">
                        <h3 class="w-full font-bold text-xl text-gray-900">{{ card.title }}</h3>
                    </div>
                    <p class="w-full font-normal text-sm  text-gray-900 md:text-base">
                        {{ card.description }}
                    </p>
                </div>
                <!-- Кнопки -->
                <div class="  px-4  ">
                    <button @click="openModal(card)" class="flex  py-2  pl-0  cursor-pointer">
                        <span class="font-medium text-sm flex  tracking-wider text-blue-600 ">
                            Подробнее
                            <Move />
                        </span>
                    </button>
                </div>
            </div>
        </div>
        <!-- кнопка -->
        <Button
            class="flex justify-center items-center px-3 py-2 w-[20%] min-w-[150px]  h-12  bg-blue-600 border-2 border-blue-600  cursor-pointer">
            <span class="px-2 md:px-4 F font-medium text-sm  text-white">
                Text
            </span>
        </Button>
        <!-- Модалка -->
        <div v-if="isModalOpen" class="fixed inset-0 bg-gray-800  flex justify-center items-center z-1000"
            @click.self="closeModal">
            <div class="bg-white p-6 rounded-lg w-[85%] h-[85%] relative mx-4">
                <button class="absolute top-2 right-2 text-4xl cursor-pointer" @click="closeModal">
                    &times;
                </button>
                <h3 class="font-bold text-xl mb-4 text-gray-900">{{ selectedCard.title }}</h3>
                <p class="font-normal text-base  text-gray-900">
                    {{ selectedCard.fullDescription }}
                </p>
            </div>
        </div>
    </section>
</template>


<script setup>
import Button from "@/components/ui/button/Button.vue"
import Move from "@/components/ui/svg/ArrowMove.vue"
import { ref } from 'vue'
import services from '@/storage/services.json';

const isModalOpen = ref(false)
const selectedCard = ref(null)
const cards = ref(services)

const openModal = (card) => {
    selectedCard.value = card
    isModalOpen.value = true
    document.body.style.overflow = 'hidden'
}

const closeModal = () => {
    isModalOpen.value = false
    document.body.style.overflow = 'auto'
}
</script>