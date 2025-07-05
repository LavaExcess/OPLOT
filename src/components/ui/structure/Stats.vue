<template>
    <section
        class="box-border flex flex-col items-center px-4 py-[40px] gap-12  w-full h-auto min-h-[300px] bg-white border-b border-gray-300 flex-none z-10">
        <div class="flex flex-col items-center w-full  gap-12 ">
            <div class="flex flex-col items-center w-full gap-2 h-auto">
                <h2 class="w-full  font-bold text-4xl  text-center text-gray-900">
                    Мы разводим — вы страдаете!
                </h2>
                <p class="w-full  font-normal text-lg text-center text-gray-900 mt-2">
                    С щенками редко гуляют, поэтому они вынуждены писать и какать прямо в квартире своей хозяйки. <br> А
                    еще им немножко скучно, поэтому они грызут гибкую подводку водопровода и воют в постоянно открытое
                    окно.
                </p>
            </div>
            <!--Утопленники-->
            <div class="flex flex-col lg:flex-row items-center justify-center w-full gap-6 h-auto">
                <div
                    class="flex flex-col items-center p-4 gap-4 w-[90%] lg:w-[302px] h-auto min-h-[80px] bg-white border border-gray-300 rounded-none flex-1">
                    <div class="flex flex-row items-center w-full gap-4 h-auto">
                        <div class="flex-shrink-0 flex justify-center items-center w-12 h-12 bg-gray-300">
                            <Sticker />
                        </div>
                        <div class="flex flex-col items-start w-full overflow-hidden">
                            <h3 class="w-full  font-bold text-xl text-gray-900 truncate">3
                            </h3>
                            <p class="w-full  font-normal text-base text-gray-600 line-clamp-2">
                                затоплены нечистотами
                            </p>
                        </div>
                    </div>
                </div>
                <!--Страдания-->
                <div
                    class="flex flex-col items-center p-4 gap-4 w-[90%] lg:w-[302px] h-auto min-h-[80px] bg-white border border-gray-300 rounded-none flex-1">
                    <div class="flex flex-row items-center w-full gap-4 h-auto">
                        <div class="flex-shrink-0 flex justify-center items-center w-12 h-12 bg-gray-300">
                            <Sheet />
                        </div>
                        <div class="flex flex-col items-start w-full overflow-hidden">
                            <h3 class="w-full  font-bold text-xl text-gray-900 truncate">20+
                            </h3>
                            <p class="w-full font-normal text-base text-gray-600 line-clamp-2">
                                страдают от страшной вони
                            </p>
                        </div>
                    </div>
                </div>
                <!--Пицца-->
                <div
                    class="flex flex-col items-center p-4 gap-4 w-[90%] lg:w-[302px] h-auto min-h-[80px] bg-white border border-gray-300 rounded-none flex-1">
                    <div class="flex flex-row items-center w-full gap-4 h-auto">
                        <div class="flex-shrink-0 flex justify-center items-center w-12 h-12 bg-gray-300">
                            <Pizza />
                        </div>
                        <div class="flex flex-col items-start w-full overflow-hidden">
                            <h3 class="w-full  font-bold text-xl text-gray-900 truncate">200+
                            </h3>
                            <p class="w-full  font-normal text-base text-gray-600 line-clamp-2">
                                Страдают от ночного визга
                            </p>
                        </div>
                    </div>
                </div>
                <!--Человеки-->
                <div
                    class="flex flex-col items-center p-4 gap-4 w-[90%] lg:w-[302px] h-auto min-h-[80px] bg-white border border-gray-300 rounded-none flex-1">
                    <div class="flex flex-row items-center w-full gap-4 h-auto">
                        <div class="flex-shrink-0 flex justify-center items-center w-12 h-12 bg-gray-300">
                            <Human />
                        </div>
                        <div class="flex flex-col items-start w-full overflow-hidden">
                            <h3 class="w-full  font-bold text-xl text-gray-900 truncate">10%
                            </h3>
                            <p class="w-full  font-normal text-base text-gray-600 line-clamp-2">
                                Квартиры теряют в цене *
                            </p>
                        </div>
                    </div>
                </div>
            </div>
        </div>
    </section>
</template>

<script setup>
import Sticker from "@/components/ui/svg/Sticker.vue"
import Sheet from "@/components/ui/svg/Sheet.vue"
import Pizza from "@/components/ui/svg/Pizza.vue"
import Human from "@/components/ui/svg/Human.vue"
</script>