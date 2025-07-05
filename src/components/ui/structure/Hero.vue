<template>
    <section
        class="flex flex-col md:flex-row items-center px-4 md:px-20 py-12 md:py-[160px] gap-8 md:gap-20 w-full min-h-screen md:h-screen bg-gray-50 z-0">
        <!-- SVG -->
        <div class="relative w-full md:w-[50%] h-auto pt-16 flex justify-center">
            <Hero />
        </div>
        <!-- TEXT -->
        <div class="flex flex-col items-start w-full md:w-[50%] h-auto  py-0 md:py-8 gap-12 md:gap-16 flex-none">
            <div class="flex flex-col items-start w-full gap-6 md:gap-12 h-auto md:h-[261px]">
                <div class="flex flex-col items-center w-full gap-1 md:gap-2 h-auto md:h-[113px]">
                    <h1 class="w-full font-bold text-4xl md:text-[2.5rem] text-gray-900 text-center md:text-left">
                        Убийственная вонь
                    </h1>
                    <h2 class="w-full font-bold text-2xl  md:text-[2rem]  text-gray-900 text-center md:text-left">
                        в доме Маринеско
                    </h2>
                </div>
                <p class="w-full lg:w-[70%]  font-normal text-base md:text-lg  text-gray-900 text-center md:text-left ">
                    Эта история о том, как жительница Кронштадта занялась разведением щенков французского бульдога в
                    своей квартире, превращая жизнь всех соседей по подъезду в <span class="font-bold"> вонючий и
                        визгливый ад! </span>
                </p>
            </div>
            <div
                class="flex flex-col md:flex-row justify-center md:justify-start items-center w-full md:w-[184px] gap-4 h-auto md:h-14 relative md:pt-2">
                <Button
                    class="flex justify-center items-center px-3 py-2 w-[133px] md:w-[184px] h-10 md:h-14 bg-blue-600 border-2 border-blue-600 cursor-pointer">
                    <span class="px-2 md:px-4  font-medium text-sm  tracking-[0.5px] text-white">
                        Text
                    </span>
                </Button>
            </div>
        </div>
    </section>
</template>
<script setup>
import Button from "@/components/ui/button/Button.vue"
import Hero from "@/components/ui/svg/Hero.vue"
</script>