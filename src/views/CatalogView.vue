<script setup lang="ts">
import { defineComponent } from 'vue'
</script>
<template>
  <div>
    <div class="w-full bg-[#996B60]">
      <div class="">
        <div
          class="menu sticky-menu top-0 z-20 flex w-full items-center justify-between bg-transparent px-[60px] py-[24px] uppercase leading-[18px] tracking-wide text-white transition-all"
        >
          <div class="flex items-center gap-5 text-sm font-normal">
            <RouterLink to="/">Главная</RouterLink>

            <RouterLink to="/catalog">Каталог</RouterLink>
            <RouterLink to="/about">О Нас</RouterLink>
          </div>
          <img src="@/assets/Logo.svg" alt="" />
          <div class="flex w-1/4 items-center gap-5 text-sm font-normal">
            <!-- <p>Главная</p>
            <p>Главная</p>
            <p>Главная</p> -->
          </div>
        </div>
      </div>
    </div>
    <section class="container mx-auto mb-[48px] mt-[66px] px-2">
      <div
        class="relative overflow-hidden rounded-[24px] bg-[#F3F3F3] pb-[56px] md:pl-[76px] pt-[48px]"
      >
        <div
          class="absolute bottom-0 md:right-0 md:top-0 z-0 h-1/6 md:h-full w-full md:w-1/6 bg-[url('@/assets/backCat1.png')] bg-cover"
        ></div>
        <div
          class="flex flex-col gap-[20px] md:gap-0 md:flex-row md:max-h-[445px] items-center justify-between"
        >
          <div class="px-8 md:px-0 md:w-2/3 font-sans">
            <p
              class="leading-11 text-[22px] md:text-[33px] lg:text-[48px] font-[600] text-gray-800 mb-[12px] transition-all duration-700"
              :class="clide ? '' : 'opacity-0 translate-x-[3%]'"
            >
              Освежите свой творческий потенциал с <br />
              <span class="font-[700]"> Драм-машиной</span>
            </p>
            <p
              class="text-[11px] md:text-[13px] lg:text-base font-light leading-[28px] mb-[21px] transition-all duration-700 delay-200"
              :class="clide ? '' : 'opacity-0 -translate-x-[3%]'"
            >
              С легкостью экспериментируйте с различными ритмами и стилями, вдохновляйтесь и
              воплощайте свои музыкальные идеи в жизнь с Драм-машины. Погрузитесь в мир музыкального
              творчества и откройте новые горизонты вашего звучания уже сегодня!
            </p>
            <div
              class="flex items-center justify-start gap-[17px] mb-[25px] transition-all duration-[700ms] delay-500"
              :class="clide ? '' : 'opacity-0 translate-y-[10%]'"
            >
              <span
                ><svg
                  xmlns="http://www.w3.org/2000/svg"
                  width="46"
                  height="46"
                  viewBox="0 0 46 46"
                  fill="none"
                >
                  <path
                    d="M36.2648 21.7765C35.4964 20.047 34.3793 18.4947 32.9835 17.2167L31.8317 16.1599C31.7926 16.125 31.7455 16.1002 31.6946 16.0877C31.6437 16.0753 31.5905 16.0755 31.5397 16.0884C31.4889 16.1013 31.442 16.1265 31.4032 16.1617C31.3644 16.1969 31.3349 16.2411 31.3171 16.2905L30.8026 17.7669C30.482 18.6931 29.8922 19.6391 29.057 20.5692C29.0016 20.6286 28.9383 20.6444 28.8948 20.6484C28.8512 20.6523 28.7839 20.6444 28.7246 20.589C28.6691 20.5415 28.6414 20.4703 28.6454 20.399C28.7918 18.0162 28.0794 15.3286 26.5199 12.4036C25.2295 9.97329 23.4365 8.07734 21.1962 6.75532L19.5615 5.79349C19.3477 5.66683 19.0746 5.83307 19.0865 6.08244L19.1736 7.98234C19.2329 9.28061 19.0825 10.4285 18.7263 11.3824C18.2909 12.55 17.6655 13.6346 16.866 14.6083C16.3096 15.285 15.6789 15.897 14.9859 16.433C13.3167 17.7161 11.9595 19.3601 11.0159 21.2421C10.0745 23.1405 9.58416 25.2306 9.58301 27.3495C9.58301 29.2177 9.95111 31.0266 10.6794 32.7326C11.3826 34.3751 12.3975 35.8657 13.6678 37.1221C14.9502 38.3888 16.4385 39.3862 18.097 40.0789C19.8148 40.7993 21.6355 41.1634 23.5157 41.1634C25.3958 41.1634 27.2165 40.7993 28.9343 40.0828C30.5887 39.3942 32.0931 38.3899 33.3635 37.1261C34.6459 35.8595 35.6513 34.3792 36.3519 32.7365C37.0791 31.0352 37.4521 29.2037 37.4483 27.3535C37.4483 25.4219 37.0525 23.5457 36.2648 21.7765V21.7765Z"
                    fill="#E55C5C"
                  /></svg
              ></span>
              <p class="text-[42px] font-[600]">71 990 р</p>
              <strike class="text-[#70737C] text-[22px]">102 990 р</strike>
            </div>
            <div
              class="flex items-center justify-start gap-[12px] transition-all duration-[700ms] delay-700"
              :class="clide ? '' : 'opacity-0 translate-y-[10%]'"
            >
              <div
                class="px-[33px] py-[11px] text-black bg-white hover:text-white :bg-black rounded-lg justify-start items-start gap-2.5 inline-flex transition-all duration-[200ms]"
              >
                <RouterLink
                  to="/product/14"
                  class="text-[11px] md:text-[13px] lg:text-base font-medium leading-7"
                >
                  Перейти к товару
                </RouterLink>
              </div>
              <div
                class="px-[33px] py-[11px] text-black bg-white hover:text-white :bg-black rounded-lg justify-start items-start gap-2.5 inline-flex transition-all duration-[200ms]"
              >
                <a
                  href="#catal"
                  class="text-[11px] md:text-[13px] lg:text-base font-medium leading-7"
                >
                  Посмотреть остальное
                </a>
              </div>
            </div>
          </div>
          <div
            class="relative z-10 h-[349px] w-[349px] rounded-t-[12px] md:rounded-l-[12px] bg-[url('@/assets/backCat2.png')] bg-cover bg-center transition-all duration-[1000ms] delay-200"
            :class="clide ? '' : 'opacity-0 translate-x-[100%]'"
          ></div>
        </div>
      </div>
    </section>
    <section class="container mx-auto">
      <div class="font-sans flex items-center justify-between mb-[40px]">
        <p class="text-gray-800 text-4xl font-semibold">Каталог продуктов</p>
        <div
          @click="showAllProducts"
          class="px-[33px] py-[11px] bg-white rounded-lg border border-zinc-100 justify-start items-start gap-2.5 inline-flex hover:bg-green-500 hover:border-green-500 group transition-all duration-300"
        >
          <p class="text-green-600 text-base font-medium leading-7 group-hover:text-white">
            Посмотреть все ({{ products.length }})
          </p>
        </div>
      </div>
      <div class="flex items-center justify-start gap-[12px] mb-[32px]" id="catal">
        <div
          @click="selectedType = 'гитара'"
          class="px-[13px] py-[19px] rounded-lg border-2 border-zinc-100 hover:border-zinc-300 hover:shadow-md justify-center items-center inline-flex"
        >
          <div class="self-stretch justify-center items-center gap-4 inline-flex">
            <img class="w-[34px] h-[34px]" src="@/assets/5iocn-1.png" />
            <div
              class="text-center text-gray-800 text-sm font-normal font-['Lexend'] leading-[24.95px]"
            >
              Гитары
            </div>
          </div>
        </div>
        <div
          @click="selectedType = 'ударный инструмент'"
          class="px-[13px] py-[19px] rounded-lg border-2 border-zinc-100 hover:border-zinc-300 hover:shadow-md justify-center items-center inline-flex"
        >
          <div class="self-stretch justify-center items-center gap-4 inline-flex">
            <img class="w-[34px] h-[34px]" src="@/assets/4iocn.png" />
            <div
              class="text-center text-gray-800 text-sm font-normal font-['Lexend'] leading-[24.95px]"
            >
              Ударные
            </div>
          </div>
        </div>
        <div
          @click="selectedType = 'клавишный инструмент'"
          class="px-[13px] py-[19px] rounded-lg border-2 border-zinc-100 hover:border-zinc-300 hover:shadow-md justify-center items-center inline-flex"
        >
          <div class="self-stretch justify-center items-center gap-4 inline-flex">
            <img class="w-[34px] h-[34px]" src="@/assets/5iocn-2.png" />
            <div
              class="text-center text-gray-800 text-sm font-normal font-['Lexend'] leading-[24.95px]"
            >
              Клавишные
            </div>
          </div>
        </div>
      </div>
      <div class="flex items-center justify-center md:justify-between flex-wrap gap-[30px]">
        <RouterLink
          :to="{ name: 'product', params: { id: item.id } }"
          v-for="item in filteredProducts"
          :key="item.id"
          class="flex flex-col gap-[24px] p-[28px] rounded-lg border-2 border-zinc-100 hover:border-zinc-300 hover:shadow-md font-sans hover:scale-[1.05] transition-all"
        >
          <img class="w-[294px] min-h-[294px] object-contain" :src="item.img" alt="" />
          <div class="flex flex-col gap-[36px]">
            <div class="">
              <div class="flex items-center justify-start gap-[1px]">
                <!-- звезды для отзыва -->
                <svg
                  v-for="star in item.stars"
                  :key="star"
                  xmlns="http://www.w3.org/2000/svg"
                  width="16"
                  height="16"
                  viewBox="0 0 16 16"
                  fill="none"
                >
                  <path
                    d="M14.6663 6.73331C14.733 6.39998 14.4663 5.99998 14.133 5.99998L10.333 5.46665L8.59967 1.99998C8.53301 1.86665 8.46634 1.79998 8.33301 1.73331C7.99967 1.53331 7.59967 1.66665 7.39967 1.99998L5.73301 5.46665L1.93301 5.99998C1.73301 5.99998 1.59967 6.06665 1.53301 6.19998C1.26634 6.46665 1.26634 6.86665 1.53301 7.13331L4.26634 9.79998L3.59967 13.6C3.59967 13.7333 3.59967 13.8666 3.66634 14C3.86634 14.3333 4.26634 14.4666 4.59967 14.2666L7.99967 12.4666L11.3997 14.2666C11.4663 14.3333 11.5997 14.3333 11.733 14.3333C11.7997 14.3333 11.7997 14.3333 11.8663 14.3333C12.1997 14.2666 12.4663 13.9333 12.3997 13.5333L11.733 9.73331L14.4663 7.06665C14.5997 6.99998 14.6663 6.86665 14.6663 6.73331Z"
                    fill="#FFCF55"
                  />
                </svg>
                <!-- коилчество отзывов -->
                <p class="text-zinc-500 text-sm font-normal leading-[24.95px] ml-[13px]">
                  ({{ item.reviews }})
                </p>
              </div>
              <!-- назввание товара -->
              <p class="text-zinc-500 text-sm font-normal leading-[24.95px]">
                {{ item.type }}
              </p>
              <p class="text-gray-800 text-base font-medium leading-[25px] max-w-[294px]">
                {{ item.name }}
              </p>
            </div>
            <div class="flex items-center justify-between">
              <!-- цена товара -->
              <p class="text-gray-800 text-[28px] font-semibold leading-[54px]">{{ item.price }}</p>
              <div
                class="p-3 rounded-lg border border-zinc-100 justify-center items-center inline-flex"
              >
                Обзор
              </div>
            </div>
          </div>
        </RouterLink>
      </div>
    </section>
    <section class="container mx-auto mt-[89px] mb-[35px]">
      <div class="">
        <div class="font-sans flex items-center justify-start mb-[40px]">
          <p class="text-gray-800 text-4xl font-semibold">Новостной блог</p>
        </div>
        <div class="flex flex-col md:flex-row items-center gap-4 md:gap-8 w-full font-sans">
          <div class="flex flex-col gap-4 md:gap-8 md:w-2/3">
            <div
              class="bg-[#EFEFEF] w-full py-[10px] md:h-[300px] rounded-[12px] pl-[30px] flex items-center justify-between overflow-hidden gap-[10px]"
            >
              <div class="">
                <div class="flex items-center gap-[8px] font-semibold mb-[8px]">
                  <svg
                    xmlns="http://www.w3.org/2000/svg"
                    width="24"
                    height="24"
                    viewBox="0 0 24 24"
                    fill="none"
                  >
                    <path
                      d="M12 3C7.05 3 3 7.05 3 12C3 16.95 7.05 21 12 21C16.95 21 21 16.95 21 12C21 7.05 16.95 3 12 3ZM14.7 12.9H12C11.46 12.9 11.1 12.54 11.1 12V7.5C11.1 6.96 11.46 6.6 12 6.6C12.54 6.6 12.9 6.96 12.9 7.5V11.1H14.7C15.24 11.1 15.6 11.46 15.6 12C15.6 12.54 15.24 12.9 14.7 12.9Z"
                      fill="#70737C"
                    />
                  </svg>
                  <p class="text-[14px] text-[#70737C]">12.09.2021</p>
                </div>
                <p class="text-[24px] font-[600] mb-[4px]">
                  Революция в музыкальной индустрии: запуск новой платформы для онлайн-коллабораций!
                </p>

                <p class="text-[14px] text-[#70737C] mb-[14px]">
                  Новая платформа предлагает музыкантам со всего мира уникальную возможность
                  сотрудничать над музыкальными проектами в режиме реального времени...
                </p>
                <div
                  class="w-[106px] h-[51px] px-[33px] py-[11px] bg-white rounded-lg border border-zinc-100 justify-start items-start gap-2.5 hover:bg-green-500 hover:border-green-500 group transition-all duration-300 inline-flex"
                >
                  <div
                    class="text-green-600 text-base font-medium leading-7 group-hover:text-white"
                  >
                    Read
                  </div>
                </div>
              </div>
              <div class="img-block-1"><img src="@/assets/blog1.png" alt="" /></div>
            </div>
            <div class="flex flex-col md:flex-row gap-4 md:gap-8">
              <div class="bg-[#EFEFEF] w-full h-[300px] rounded-[12px] relative overflow-hidden">
                <div
                  class="absolute z-0 bottom-0 right-0 w-[238px] h-[238px] bg-[url('@/assets/blog2.png')] translate-x-1/4 translate-y-1/3 bg-center bg-cover rounded-full"
                ></div>
                <div class="relative z-10 flex flex-col p-[30px]">
                  <div class="flex items-center gap-[8px] font-semibold mb-[8px]">
                    <svg
                      xmlns="http://www.w3.org/2000/svg"
                      width="24"
                      height="24"
                      viewBox="0 0 24 24"
                      fill="none"
                    >
                      <path
                        d="M12 3C7.05 3 3 7.05 3 12C3 16.95 7.05 21 12 21C16.95 21 21 16.95 21 12C21 7.05 16.95 3 12 3ZM14.7 12.9H12C11.46 12.9 11.1 12.54 11.1 12V7.5C11.1 6.96 11.46 6.6 12 6.6C12.54 6.6 12.9 6.96 12.9 7.5V11.1H14.7C15.24 11.1 15.6 11.46 15.6 12C15.6 12.54 15.24 12.9 14.7 12.9Z"
                        fill="#70737C"
                      />
                    </svg>
                    <p class="text-[14px] text-[#70737C]">12.09.2021</p>
                  </div>
                  <p class="text-[24px] font-[600] mb-[4px]">
                    Запуск интеллектуального плагина для создания композиций!
                  </p>
                  <div
                    class="w-[106px] h-[51px] px-[33px] py-[11px] bg-white rounded-lg border border-zinc-100 justify-start items-start gap-2.5 inline-flex hover:bg-green-500 hover:border-green-500 group transition-all duration-300"
                  >
                    <div
                      class="text-green-600 text-base font-medium leading-7 group-hover:text-white"
                    >
                      Read
                    </div>
                  </div>
                </div>
              </div>
              <div class="bg-[#EFEFEF] w-full h-[300px] rounded-[12px] relative overflow-hidden">
                <div
                  class="absolute z-0 bottom-0 right-0 w-[238px] h-[238px] bg-[url('@/assets/blog3.png')] translate-x-1/4 translate-y-1/3 bg-center bg-cover rounded-full"
                ></div>
                <div class="relative z-10 flex flex-col p-[30px]">
                  <div class="flex items-center gap-[8px] font-semibold mb-[8px]">
                    <svg
                      xmlns="http://www.w3.org/2000/svg"
                      width="24"
                      height="24"
                      viewBox="0 0 24 24"
                      fill="none"
                    >
                      <path
                        d="M12 3C7.05 3 3 7.05 3 12C3 16.95 7.05 21 12 21C16.95 21 21 16.95 21 12C21 7.05 16.95 3 12 3ZM14.7 12.9H12C11.46 12.9 11.1 12.54 11.1 12V7.5C11.1 6.96 11.46 6.6 12 6.6C12.54 6.6 12.9 6.96 12.9 7.5V11.1H14.7C15.24 11.1 15.6 11.46 15.6 12C15.6 12.54 15.24 12.9 14.7 12.9Z"
                        fill="#70737C"
                      />
                    </svg>
                    <p class="text-[14px] text-[#70737C]">12.09.2021</p>
                  </div>
                  <p class="text-[24px] font-[600] mb-[4px]">
                    Представление нового формата звукозаписи в высоком разрешении!
                  </p>
                  <div
                    class="w-[106px] h-[51px] px-[33px] py-[11px] bg-white rounded-lg border border-zinc-100 justify-start items-start gap-2.5 inline-flex hover:bg-green-500 hover:border-green-500 group transition-all duration-300"
                  >
                    <div
                      class="text-green-600 text-base font-medium leading-7 group-hover:text-white"
                    >
                      Read
                    </div>
                  </div>
                </div>
              </div>
            </div>
          </div>
          <div
            class="relative bg-[#EFEFEF] w-full h-[300px] md:w-1/3 md:h-[630px] rounded-[12px] overflow-hidden"
          >
            <div
              class="absolute z-0 bottom-0 right-0 w-[267px] h-[366px] bg-[url('@/assets/blog5.png')] translate-x-1/4 translate-y-1/4 bg-center bg-cover rounded-t-[70px]"
            ></div>
            <div class="relative z-10 flex flex-col p-[30px]">
              <div class="flex items-center gap-[8px] font-semibold mb-[8px]">
                <svg
                  xmlns="http://www.w3.org/2000/svg"
                  width="24"
                  height="24"
                  viewBox="0 0 24 24"
                  fill="none"
                >
                  <path
                    d="M12 3C7.05 3 3 7.05 3 12C3 16.95 7.05 21 12 21C16.95 21 21 16.95 21 12C21 7.05 16.95 3 12 3ZM14.7 12.9H12C11.46 12.9 11.1 12.54 11.1 12V7.5C11.1 6.96 11.46 6.6 12 6.6C12.54 6.6 12.9 6.96 12.9 7.5V11.1H14.7C15.24 11.1 15.6 11.46 15.6 12C15.6 12.54 15.24 12.9 14.7 12.9Z"
                    fill="#70737C"
                  />
                </svg>
                <p class="text-[14px] text-[#70737C]">12.09.2021</p>
              </div>
              <p class="text-[24px] font-[600] mb-[4px]">
                Революционная технология виртуальной реальности для концертного просмотра!
              </p>
              <p class="text-[14px] text-[#70737C] mb-[14px]">
                Новая технология VR позволяет зрителям погрузиться в музыкальные концерты и
                фестивали, не выходя из дома...
              </p>
              <div
                class="w-[106px] h-[51px] px-[33px] py-[11px] bg-white rounded-lg border border-zinc-100 justify-start items-start gap-2.5 inline-flex hover:bg-green-500 hover:border-green-500 group transition-all duration-300"
              >
                <div class="text-green-600 text-base font-medium leading-7 group-hover:text-white">
                  Read
                </div>
              </div>
            </div>
          </div>
        </div>
      </div>
    </section>
  </div>
</template>

<script lang="ts">
export default defineComponent({
  data() {
    return {
      selectedType: '',
      products: [
        {
          id: 1,
          img: '../src/assets/gitar1.png',
          stars: 4,
          reviews: 123,
          name: 'IBANEZ GSA60-BKN',
          price: '788 000 р.',
          type: 'гитара'
        },
        {
          id: 2,
          img: '../src/assets/clav1.webp',
          stars: 5,
          reviews: 78,
          name: 'Синтезатор Casio CT-S200BK',
          price: '25 000 р.',
          type: 'клавишный инструмент'
        },
        {
          id: 3,
          img: '../src/assets/bubny1.webp',
          stars: 4,
          reviews: 56,
          name: 'PODFL422MN Fuse Limited',
          price: '62 900 р.',
          type: 'ударный инструмент'
        },
        {
          id: 4,
          img: '../src/assets/gitar2.png',
          stars: 4,
          reviews: 89,
          name: 'Fender Stratocaster',
          price: '98 500 р.',
          type: 'гитара'
        },
        {
          id: 5,
          img: '../src/assets/klavishi2.webp',
          stars: 4,
          reviews: 45,
          name: 'Синтезатор Casio CT-S200DK',
          price: '25 900 р.',
          type: 'клавишный инструмент'
        },
        {
          id: 6,
          img: '../src/assets/bubny2.webp',
          stars: 5,
          reviews: 102,
          name: 'Ударная установка электронная Medeli MZ520',
          price: '65 050 р.',
          type: 'ударный инструмент'
        },
        {
          id: 7,
          img: '../src/assets/gitar3.png',
          stars: 5,
          reviews: 97,
          name: 'Gibson Les Paul Standard',
          price: '125 000 р.',
          type: 'гитара'
        },
        {
          id: 8,
          img: '../src/assets/klavishi3.webp',
          stars: 4,
          reviews: 62,
          name: 'Синтезатор Kurzweil KP70 LB',
          price: '36 500 р.',
          type: 'клавишный инструмент'
        },
        {
          id: 9,
          img: '../src/assets/bubny3.webp',
          stars: 4,
          reviews: 58,
          name: 'Электронная ударная установка Hitman HD-17',
          price: '53 599 р.',
          type: 'ударный инструмент'
        },
        {
          id: 10,
          img: '../src/assets/gitar4.png',
          stars: 4,
          reviews: 84,
          name: 'PRS SE Custom 24',
          price: '87 800 р.',
          type: 'гитара'
        },
        {
          id: 11,
          img: '../src/assets/klavishi4.webp',
          stars: 5,
          reviews: 110,
          name: 'Синтезатор Medeli M221L',
          price: '22 000 р.',
          type: 'клавишный инструмент'
        },
        {
          id: 12,
          img: '../src/assets/gitar5.png',
          stars: 4,
          reviews: 92,
          name: 'Epiphone Les Paul Standard',
          price: '72 500 р.',
          type: 'гитара'
        },
        {
          id: 13,
          img: '../src/assets/klavishi5.webp',
          stars: 4,
          reviews: 68,
          name: 'Синтезатор Medeli A300',
          price: '28 900 р.',
          type: 'клавишный инструмент'
        },
        {
          id: 14,
          img: '../src/assets/bubny4.webp',
          stars: 5,
          reviews: 105,
          name: 'Драм-машина Novation Circuit Tracks Groovebox',
          price: '71 990 р.',
          type: 'ударный инструмент'
        },
        {
          id: 15,
          img: '../src/assets/gitar6.png',
          stars: 5,
          reviews: 81,
          name: 'Gretsch G5420T Electromatic',
          price: '94 200 р.',
          type: 'гитара'
        }
      ],
      clide: false
    }
  },
  mounted() {
    setTimeout(() => {
      this.clide = true
    }, 500)
  },
  computed: {
    filteredProducts() {
      if (this.selectedType) {
        return this.products.filter((product) => product.type === this.selectedType)
      } else {
        return this.products
      }
    }
  },
  methods: {
    showAllProducts() {
      this.selectedType = ''
    }
  }
})
</script>

<style></style>
