<script lang="ts" setup>
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
    <section class="section-1 container mx-auto my-[85px] flex justify-between items-center">
      <div class="grid grid-cols-2 w-1/2 gap-[30px]">
        <div class="grid grid-cols-1 gap-[30px] mt-[50px]">
          <div
            class="panel w-full h-full rounded-2xl bg-[#EEEEEE] font-bold text-[20px] text-[#222831] p-[20px]"
          >
            <p class="mb-3">Страховка</p>
            <p class="font-semibold text-[16px]">
              Не волнуйтесь о поломках, все инструменты застрахованы, поэтому при неудачах вы
              защищены от лишних трат.
            </p>
          </div>
          <div
            class="panel w-full h-full rounded-2xl bg-[#00ADB5] font-bold text-[20px] text-[#EEEEEE] p-[20px]"
          >
            <p class="mb-3">Удобство</p>
            <p class="font-semibold text-[16px]">
              Наши шоурумы расположены по всей России, вы сможе лично убедиться в качестве или
              заказать доставку.
            </p>
          </div>
        </div>
        <div class="grid grid-cols-1 gap-[30px] mb-[50px]">
          <div
            class="panel w-full h-full rounded-2xl bg-[#393E46] font-bold text-[20px] text-[#EEEEEE] p-[20px]"
          >
            <p class="mb-3">Доступность</p>
            <p class="font-semibold text-[16px]">
              Мы предоставляем возможность экономить, как крупным студиям, так и небольшим группам,
              предлагая аренду по низкой цене!
            </p>
          </div>
          <div
            class="panel w-full h-full rounded-2xl bg-[#222831] font-bold text-[20px] text-[#00ADB5] p-[20px]"
          >
            <p class="mb-3">Выбор</p>
            <p class="font-semibold text-[16px]">
              В нашем каталоге представлен большой выбор различных инструмантов, которые доступны
              каждому из вас.
            </p>
          </div>
        </div>
      </div>

      <div class="masterimg w-1/2">
        <img class="transformDD orig w-full" src="@/assets/bgWallpaper.png" alt="" />
      </div>
    </section>
    <section class="text-gray-600 body-font">
      <div class="container px-5 py-24 mx-auto flex flex-wrap">
        <div class="flex w-full mb-20 flex-wrap">
          <h1
            class="sm:text-3xl text-2xl font-medium title-font text-gray-900 lg:w-1/3 lg:mb-0 mb-4"
          >
            Чем мы помогаем
          </h1>
          <p class="lg:pl-6 lg:w-2/3 mx-auto leading-relaxed text-base">
            Мы предоставляем оборудование и инструманты на прокат. Многие мазыканты и артисты
            предпочитают большим тратам на покупку, аренду на время концерта или тура.
          </p>
        </div>
        <div class="flex flex-wrap md:-m-2 -m-1">
          <div class="flex flex-wrap w-full md:w-1/2">
            <div class="md:p-2 p-1 w-full sm:w-1/2">
              <img
                alt="gallery"
                class="w-full object-cover h-full object-center block"
                src="https://i.pinimg.com/564x/29/c5/a2/29c5a2fad027b0b762267f16292e12d8.jpg"
              />
            </div>
            <div class="md:p-2 p-1 w-full sm:w-1/2">
              <img
                alt="gallery"
                class="w-full object-cover h-full object-center block"
                src="https://i.pinimg.com/564x/1c/3c/7e/1c3c7eb7d49bf4d668f702ae602087c5.jpg"
              />
            </div>
            <div class="md:p-2 p-1 w-full">
              <img
                alt="gallery"
                class="w-full h-full object-cover object-center block"
                src="https://i.pinimg.com/564x/4b/67/79/4b67794cfcadd6fc3571ea3bcbe868c6.jpg"
              />
            </div>
          </div>
          <div class="flex flex-wrap w-full md:w-1/2">
            <div class="md:p-2 p-1 w-full">
              <img
                alt="gallery"
                class="w-full h-full object-cover object-center block"
                src="https://i.pinimg.com/564x/03/1d/94/031d940dec1448a484e61b309dbd60a0.jpg"
              />
            </div>
            <div class="md:p-2 p-1 w-full sm:w-1/2">
              <img
                alt="gallery"
                class="w-full object-cover h-full object-center block"
                src="https://i.pinimg.com/564x/a6/75/98/a675981d5a332c3680df351d3d3bbac2.jpg"
              />
            </div>
            <div class="md:p-2 p-1 w-full sm:w-1/2">
              <img
                alt="gallery"
                class="w-full object-cover h-full object-center block"
                src="https://i.pinimg.com/564x/ef/b8/4e/efb84eba2a6a6111e0479f619055f468.jpg"
              />
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
    return {}
  }
})
</script>

<style scoped>
.masterimg {
  perspective: 1000px;
}
.transformDD {
  transform: rotateX(1deg) rotateY(-20deg);
  transform-style: preserve-3d;
}
</style>
