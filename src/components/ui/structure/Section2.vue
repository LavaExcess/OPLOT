<template>
    <section
        class="box-border flex flex-col items-center px-4 py-[40px] gap-12  w-full h-auto min-h-[300px] bg-white border-b border-gray-300 flex-none z-10">
        <div class="flex flex-col items-center w-full  gap-12 ">
            <div class="flex flex-col items-center w-full gap-2 h-auto">
                <h2 class="w-full font-roboto font-bold text-4xl  text-center text-gray-900">
                    Мы разводим — вы страдаете!
                </h2>
                <p class="w-full font-roboto font-normal text-lg text-center text-gray-900 mt-2">
                    С щенками редко гуляют, поэтому они вынуждены писать и какать прямо в квартире своей хозяйки.
                    <br> А
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
                            <svg class="w-6 h-6 text-gray-600" viewBox="0 0 24 24" fill="none">
                                <path
                                    d="M8 15C8 15 9.5 17 12 17C14.5 17 16 15 16 15M9 9H9.01M15 9H15.01M22 12C22 17.5228 17.5228 22 12 22C6.47715 22 2 17.5228 2 12C2 6.47715 6.47715 2 12 2C17.5228 2 22 6.47715 22 12Z"
                                    stroke="currentColor" stroke-width="2" stroke-linecap="round"
                                    stroke-linejoin="round" />
                            </svg>
                        </div>

                        <div class="flex flex-col items-start w-full overflow-hidden">
                            <h3 class="w-full font-roboto font-bold text-xl text-gray-900 truncate">3
                            </h3>
                            <p class="w-full font-roboto font-normal text-base text-gray-600 line-clamp-2">
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
                            <svg class="w-6 h-6 text-gray-600" viewBox="0 0 24 24" fill="none">
                                <path
                                    d="M14 2H6C5.46957 2 4.96086 2.21071 4.58579 2.58579C4.21071 2.96086 4 3.46957 4 4V20C4 20.5304 4.21071 21.0391 4.58579 21.4142C4.96086 21.7893 5.46957 22 6 22H18C18.5304 22 19.0391 21.7893 19.4142 21.4142C19.7893 21.0391 20 20.5304 20 20V8L14 2Z"
                                    stroke="currentColor" stroke-width="2" stroke-linecap="round"
                                    stroke-linejoin="round" />
                                <path d="M14 2V8H20" stroke="currentColor" stroke-width="2" stroke-linecap="round"
                                    stroke-linejoin="round" />
                            </svg>
                        </div>

                        <div class="flex flex-col items-start w-full overflow-hidden">
                            <h3 class="w-full font-roboto font-bold text-xl text-gray-900 truncate">20+
                            </h3>
                            <p class="w-full font-roboto font-normal text-base text-gray-600 line-clamp-2">
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
                            <svg class="w-6 h-6 text-gray-600 " viewBox="0 0 20 20" fill="none">
                                <path
                                    d="M4.25798 6.88406L9.96998 16.9771L15.588 7.14706C14.258 7.04206 12.876 6.69406 11.346 6.15506C10.951 6.01506 10.748 5.98406 10.566 6.00706C10.412 6.02706 8.84298 6.57606 7.92298 6.80906C6.76198 7.10306 5.53898 7.12606 4.25798 6.88406ZM2.84798 4.39406C4.54998 5.06406 6.07198 5.21406 7.43198 4.87006C8.16998 4.68306 9.90998 4.07406 10.315 4.02306C10.844 3.95606 11.345 4.03306 12.011 4.26806C13.785 4.89406 15.307 5.22406 16.714 5.17706L17.601 3.62506C15.2 2.54825 12.5974 1.99433 9.96598 2.00006C7.35889 1.99455 4.77988 2.53836 2.39698 3.59606L2.84798 4.39306V4.39406ZM0.541977 2.26806C3.45695 0.769882 6.68855 -0.00783934 9.96598 5.95722e-05C13.328 5.95722e-05 16.572 0.80006 19.462 2.30606C19.5813 2.36826 19.6869 2.45392 19.7723 2.55789C19.8578 2.66187 19.9214 2.78202 19.9593 2.91116C19.9972 3.0403 20.0087 3.17575 19.993 3.30942C19.9773 3.44309 19.9348 3.57221 19.868 3.68906L10.834 19.4961C10.7463 19.6493 10.6196 19.7766 10.4667 19.8649C10.3139 19.9533 10.1404 19.9997 9.96381 19.9993C9.78726 19.9988 9.61397 19.9517 9.46154 19.8626C9.30911 19.7735 9.18298 19.6457 9.09598 19.4921L0.129977 3.65006C0.0638986 3.53298 0.0221075 3.40377 0.00710242 3.27017C-0.00790266 3.13657 0.00418643 3.00131 0.0426469 2.87249C0.0811074 2.74366 0.145149 2.62392 0.230944 2.52041C0.316739 2.4169 0.422525 2.33175 0.541977 2.27006V2.26806ZM7.99998 10.0001C7.73476 10.0001 7.48041 9.8947 7.29287 9.70717C7.10533 9.51963 6.99998 9.26528 6.99998 9.00006C6.99998 8.73484 7.10533 8.48049 7.29287 8.29295C7.48041 8.10542 7.73476 8.00006 7.99998 8.00006C8.26519 8.00006 8.51955 8.10542 8.70708 8.29295C8.89462 8.48049 8.99998 8.73484 8.99998 9.00006C8.99998 9.26528 8.89462 9.51963 8.70708 9.70717C8.51955 9.8947 8.26519 10.0001 7.99998 10.0001ZM11 13.0001C10.7348 13.0001 10.4804 12.8947 10.2929 12.7072C10.1053 12.5196 9.99998 12.2653 9.99998 12.0001C9.99998 11.7348 10.1053 11.4805 10.2929 11.293C10.4804 11.1054 10.7348 11.0001 11 11.0001C11.2652 11.0001 11.5195 11.1054 11.7071 11.293C11.8946 11.4805 12 11.7348 12 12.0001C12 12.2653 11.8946 12.5196 11.7071 12.7072C11.5195 12.8947 11.2652 13.0001 11 13.0001Z"
                                    fill="#697077" />
                            </svg>
                        </div>


                        <div class="flex flex-col items-start w-full overflow-hidden">
                            <h3 class="w-full font-roboto font-bold text-xl text-gray-900 truncate">200+
                            </h3>
                            <p class="w-full font-roboto font-normal text-base text-gray-600 line-clamp-2">
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
                            <svg class="w-6 h-6 text-gray-600" viewBox="0 0 24 24" fill="none">
                                <path
                                    d="M17 21V19C17 17.9391 16.5786 16.9217 15.8284 16.1716C15.0783 15.4214 14.0609 15 13 15H5C3.93913 15 2.92172 15.4214 2.17157 16.1716C1.42143 16.9217 1 17.9391 1 19V21M23 21V19C22.9993 18.1137 22.7044 17.2528 22.1614 16.5523C21.6184 15.8519 20.8581 15.3516 20 15.13M16 3.13C16.8604 3.3503 17.623 3.8507 18.1676 4.55231C18.7122 5.25392 19.0078 6.11683 19.0078 7.005C19.0078 7.89317 18.7122 8.75608 18.1676 9.45769C17.623 10.1593 16.8604 10.6597 16 10.88M13 7C13 9.20914 11.2091 11 9 11C6.79086 11 5 9.20914 5 7C5 4.79086 6.79086 3 9 3C11.2091 3 13 4.79086 13 7Z"
                                    stroke="currentColor" stroke-width="2" stroke-linecap="round"
                                    stroke-linejoin="round" />
                            </svg>
                        </div>
                        <div class="flex flex-col items-start w-full overflow-hidden">
                            <h3 class="w-full font-roboto font-bold text-xl text-gray-900 truncate">10%
                            </h3>
                            <p class="w-full font-roboto font-normal text-base text-gray-600 line-clamp-2">
                                Квартиры теряют в цене *
                            </p>
                        </div>
                    </div>
                </div>



            </div>
        </div>
    </section>
</template>