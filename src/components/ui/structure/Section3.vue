<template>
    <section class="flex flex-col items-center p-12 md:p-20 gap-12 md:gap-16 w-full bg-gray-50 ">

        <Carousel :opts="carouselOptions" class="w-full max-w-[90%]  " :plugins="[Autoplay({
            delay: 5000, //АВТОПРОКРУТКА 5 СЕК
        })]">
            <CarouselContent class="ml-0 ">

                <!-- БЛОК КАРУСЕЛИ  -->
                <CarouselItem v-for="testimonial in testimonials" :key="testimonial.id" class="pl-0 basis-full   ">
                    <div
                        class="flex flex-col items-center p-6 gap-4 w-full h-[327px] bg-white rounded-lg shadow-sm   cursor-grab active:cursor-grabbing group-active:cursor-grabbing">




                        <!-- Ава -->
                        <div class="flex justify-center items-center w-16 h-16 bg-gray-200 rounded-full">
                            <svg class="w-6 h-6 text-gray-400" viewBox="0 0 24 24" fill="none"
                                xmlns="http://www.w3.org/2000/svg">
                                <path
                                    d="M20 21V19C20 17.9391 19.5786 16.9217 18.8284 16.1716C18.0783 15.4214 17.0609 15 16 15H8C6.93913 15 5.92172 15.4214 5.17157 16.1716C4.42143 16.9217 4 17.9391 4 19V21M16 7C16 9.20914 14.2091 11 12 11C9.79086 11 8 9.20914 8 7C8 4.79086 9.79086 3 12 3C14.2091 3 16 4.79086 16 7Z"
                                    stroke="currentColor" stroke-width="2" stroke-linecap="round"
                                    stroke-linejoin="round" />
                            </svg>
                        </div>


                        <!--Отзыв-->
                        <p
                            class="w-full font-roboto font-normal text-base md:text-lg  text-center text-gray-900 select-none">
                            {{ testimonial.text }}
                        </p>
                        <!--Отзыв-->
                        <div class="flex flex-col items-center w-full gap-1">
                            <h4
                                class="w-full font-roboto font-bold text-xl md:text-2xl  text-center text-gray-900 select-none">
                                {{ testimonial.category }}
                            </h4>
                            <p
                                class="w-full font-roboto font-normal text-base md:text-lg  text-center text-gray-900 select-none">
                                {{ testimonial.subcategory }}
                            </p>
                        </div>
                    </div>
                </CarouselItem>
            </CarouselContent>

            <CarouselPrevious
                class="hidden md:flex size-10 absolute left-[-50px] top-1/2 -translate-y-1/2  border-4 border-double border-gray-400 bg-transparent hover:border-gray-900 active:scale-95 active:border-gray-700 transition-all duration-200 cursor-grab active:cursor-grabbing focus-visible:outline-none focus-visible:ring-2 focus-visible:ring-gray-500" />

            <CarouselNext
                class="hidden md:flex size-10 absolute right-[-50px] top-1/2 -translate-y-1/2  border-4 border-double border-gray-400 bg-transparent hover:border-gray-900 active:scale-95 active:border-gray-700 transition-all duration-200 cursor-grab active:cursor-grabbing focus-visible:outline-none focus-visible:ring-2 focus-visible:ring-gray-500" />
        </Carousel>
    </section>
</template>



<script setup lang="ts">
import {
    Carousel,
    CarouselContent,
    CarouselItem,
    CarouselNext,
    CarouselPrevious,
} from '@/components/ui/carousel'
import type { EmblaOptionsType } from 'embla-carousel'
import Autoplay from 'embla-carousel-autoplay'


const testimonials = [
    {
        id: 1,
        text: "С щенками редко гуляют, поэтому они вынуждены писать и какать прямо в квартире своей хозяйки. А еще им немножко скучно, поэтому они грызут гибкую подводку водопровода и воют в постоянно открытое окно.",
        category: "Cергей 1",
        subcategory: "Сосед 1"
    },
    {
        id: 2,
        text: "С щенками редко гуляют, поэтому они вынуждены писать и какать прямо в квартире своей хозяйки. А еще им немножко скучно, поэтому они грызут гибкую подводку водопровода и воют в постоянно открытое окно.",
        category: "Cергей 1",
        subcategory: "Сосед 1"
    },
    {
        id: 3,
        text: "С щенками редко гуляют, поэтому они вынуждены писать и какать прямо в квартире своей хозяйки. А еще им немножко скучно, поэтому они грызут гибкую подводку водопровода и воют в постоянно открытое окно.",
        category: "Cергей 1",
        subcategory: "Сосед 1"
    },
    {
        id: 4,
        text: "С щенками редко гуляют, поэтому они вынуждены писать и какать прямо в квартире своей хозяйки. А еще им немножко скучно, поэтому они грызут гибкую подводку водопровода и воют в постоянно открытое окно.",
        category: "Cергей 1",
        subcategory: "Сосед 1"
    },
    {
        id: 5,
        text: "С щенками редко гуляют, поэтому они вынуждены писать и какать прямо в квартире своей хозяйки. А еще им немножко скучно, поэтому они грызут гибкую подводку водопровода и воют в постоянно открытое окно.",
        category: "Cергей 1",
        subcategory: "Сосед 1"
    },
]




const carouselOptions: EmblaOptionsType = {
    loop: true,
    align: 'center' as const,
    slidesToScroll: 1,
    dragFree: false,
    containScroll: 'trimSnaps'
}
</script>
