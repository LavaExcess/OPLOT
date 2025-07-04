<template>
    <section
        class="flex flex-col md:flex-row items-center px-4 md:px-20 py-12 md:py-[160px] gap-8 md:gap-20 w-full min-h-screen md:h-screen bg-gray-50 z-0">

        <!-- SVG -->

        <div class="relative w-full md:w-[50%] h-auto pt-16 flex justify-center">
            <svg class="w-[361px] h-[280px] md:w-[600px] md:h-[574px]" viewBox="0 0 600 574" fill="none"
                xmlns="http://www.w3.org/2000/svg">
                <path fill-rule="evenodd" clip-rule="evenodd"
                    d="M305.936 1.13015e-05C389.492 -0.0215874 472.261 30.9151 529.26 94.218C584.573 155.649 604.63 241.79 599.122 325.61C593.984 403.792 559.857 478.562 500.788 527.501C446.976 572.083 373.636 581.776 305.936 568.511C248.993 557.354 218.767 500.202 173.061 463.286C114.55 416.028 23.4367 400.117 5.19386 325.61C-14.9408 243.376 26.1115 155.627 82.7241 94.3334C140.48 31.8018 222.402 0.0216045 305.936 1.13015e-05Z"
                    fill="#DDE1E6" />
            </svg>
        </div>



        <!-- TEXT -->

        <div class="flex flex-col items-start w-full md:w-[50%] h-auto  py-0 md:py-8 gap-12 md:gap-16 flex-none">
            <div class="flex flex-col items-start w-full gap-6 md:gap-12 h-auto md:h-[261px]">
                <div class="flex flex-col items-center w-full gap-1 md:gap-2 h-auto md:h-[113px]">
                    <h1
                        class="w-full font-roboto font-bold text-4xl md:text-[2.5rem] text-gray-900 text-center md:text-left">
                        Убийственная вонь
                    </h1>
                    <h2
                        class="w-full font-roboto font-bold text-2xl  md:text-[2rem]  text-gray-900 text-center md:text-left">
                        в доме Маринеско
                    </h2>
                </div>
                <p
                    class="w-full lg:w-[70%] font-roboto font-normal text-base md:text-lg  text-gray-900 text-center md:text-left ">
                    Эта история о том, как жительница Кронштадта занялась разведением щенков французского бульдога в
                    своей квартире, превращая жизнь всех соседей по подъезду вонючий и визгливый ад!
                </p>
            </div>
            <div
                class="flex flex-col md:flex-row justify-center md:justify-start items-center w-full md:w-[184px] gap-4 h-auto md:h-14 relative md:pt-2">
                <Button
                    class="flex justify-center items-center px-3 py-2 w-[133px] md:w-[184px] h-10 md:h-14 bg-blue-600 border-2 border-blue-600 cursor-pointer">
                    <span class="px-2 md:px-4 font-roboto font-medium text-sm  tracking-[0.5px] text-white">
                        Text
                    </span>
                </Button>
            </div>
        </div>
    </section>
</template>



<script setup>
import Button from "@/components/ui/button/Button.vue"
</script>