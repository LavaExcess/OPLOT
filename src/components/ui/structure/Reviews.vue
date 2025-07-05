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
                            <Ava />
                        </div>
                        <p class="w-full font-normal text-base md:text-lg  text-center text-gray-900 select-none">
                            {{ testimonial.text }}
                        </p>
                        <div class="flex flex-col items-center w-full gap-1">
                            <h4 class="w-full  font-bold text-xl md:text-2xl  text-center text-gray-900 select-none">
                                {{ testimonial.category }}
                            </h4>
                            <p class="w-full  font-normal text-base md:text-lg  text-center text-gray-900 select-none">
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
import Ava from "@/components/ui/svg/Avatar.vue"
import testimonials from '@/storage/testimonials.json';



const carouselOptions: EmblaOptionsType = {
    loop: true,
    align: 'center' as const,
    slidesToScroll: 1,
    dragFree: false,
    containScroll: 'trimSnaps'
}
</script>
