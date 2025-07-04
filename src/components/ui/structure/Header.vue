<template>
    <header class="w-full h-[72px] bg-white shadow-sm fixed top-0 left-0 z-50 absolute">
        <div class="container mx-auto flex items-center justify-between h-full px-4">
            <div class="flex items-start gap-1 h-[39px]">
                <div class="flex-shrink-0 w-6 h-6 pt-2">
                    <svg width="24" height="25" viewBox="0 0 24 25" fill="none" xmlns="http://www.w3.org/2000/svg">
                        <path fill-rule="evenodd" clip-rule="evenodd"
                            d="M0 0.5V24.5H24V0.5H0ZM3.41421 2.5L12 11.0858L20.5858 2.5H3.41421ZM22 3.91421L13.4142 12.5L22 21.0858V3.91421ZM20.5858 22.5L12 13.9142L3.41421 22.5H20.5858ZM2 21.0858L10.5858 12.5L2 3.91421V21.0858Z"
                            fill="#4D5358" />
                    </svg>
                </div>
                <div class="flex flex-col justify-between">
                    <div class="font-bold text-[24px] w-full  text-gray-600">
                        Щенки бульдога
                    </div>
                    <div class="self-end text-[12px] text-gray-500 mt-[-2px]">
                        в Кронштадте
                    </div>
                </div>
            </div>

            <nav class="hidden md:flex items-center space-x-6">
                <a href="#" class="text-gray-600 hover:text-gray-900">Документы</a>
                <a href="#" class="text-gray-600 hover:text-gray-900">Новости</a>
                <a href="#" class="text-gray-600 hover:text-gray-900">Контакты</a>
            </nav>


            <button class="md:hidden flex flex-col space-y-1.5 w-6" @click="OpenMenu = !OpenMenu">
                <span class="w-full h-0.5 bg-gray-600"></span>
                <span class="w-full h-0.5 bg-gray-600"></span>
                <span class="w-full h-0.5 bg-gray-600"></span>
            </button>
        </div>


        <div v-if="OpenMenu" class="md:hidden absolute top-[72px] left-0 w-full bg-white shadow-md py-2 px-4">
            <a href="#" class="block py-2 text-gray-600 hover:text-gray-900">Документы</a>
            <a href="#" class="block py-2 text-gray-600 hover:text-gray-900">Новости</a>
            <a href="#" class="block py-2 text-gray-600 hover:text-gray-900">Контакты</a>
        </div>
    </header>
</template>

<script>
export default {
    data() {
        return {
            OpenMenu: false
        }
    }
}
</script>