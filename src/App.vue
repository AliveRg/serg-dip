<script setup lang="ts">
import { RouterLink, RouterView } from 'vue-router'
</script>

<template>
  <div class="relative">
    <header class="header">
      <div
        :class="banner ? 'h-[50px]' : 'h-0'"
        class="bg-black flex items-center justify-center text-white relative overflow-hidden transition-all"
      >
        <p>Первая личная консультация бесплатно</p>
        <svg
          @click="(banner = false), handleScroll()"
          class="absolute top-1/2 right-[50px] -translate-y-1/2"
          width="12"
          height="12"
          viewBox="0 0 12 12"
          fill="#ffffff"
          xmlns="http://www.w3.org/2000/svg"
        >
          <g clip-path="url(#clip0_1_1062)">
            <path
              fill-rule="evenodd"
              clip-rule="evenodd"
              d="M9.8995 0L11.3137 1.41421L7.071 5.657L11.3137 9.8995L9.8995 11.3137L5.657 7.071L1.41421 11.3137L0 9.8995L4.243 5.657L0 1.41421L1.41421 0L5.657 4.243L9.8995 0Z"
              fill="white"
            />
          </g>
          <defs>
            <clipPath id="clip0_1_1062">
              <rect width="12" height="12" fill="white" />
            </clipPath>
          </defs>
        </svg>
      </div>
    </header>
    <div class="relative">
      <div class="" v-if="$route.path === '/'">
        <div
          class="menu w-[80%] bg-transparent fixed top-0 flex items-center justify-between pl-[60px] py-[24px] sticky-menu z-20 text-white uppercase leading-[18px] tracking-wide transition-all"
          :class="{ sticky: stick }"
        >
          <div class="text-sm font-normal flex items-center gap-5">
            <RouterLink to="/">Главная</RouterLink>

            <RouterLink to="/catalog">Каталог</RouterLink>
            <RouterLink to="/about">О Нас</RouterLink>
          </div>
          <img src="@/assets/Logo.svg" alt="" />
          <div class="text-sm font-normal flex items-center gap-5 lg:w-1/5">
            <!-- <p>Главная</p>
            <p>Главная</p>
            <p>Главная</p> -->
          </div>
        </div>
      </div>
    </div>
    <RouterView />
    <section
      class="section-8 relative z-20 container mx-auto py-[15px] md:py-[60px] text-white font-sans flex flex-col md:flex-row gap-[30px] md:gap-0 justify-between items-start pl-[20px] pr-[10px] md:pl-[60px] md:pr-[20px]"
      @mousemove="moveBackground"
    >
      <div
        class="absolute z-10 top-0 left-0 w-full h-full bg-center attach bg-[url('@/assets/attach4.png')]"
        ref="image"
      ></div>
      <div class="flex relative z-30 flex-col gap-[22px] md:w-[40%] mx-auto">
        <div
          class="bg-black/70 md:bg-black px-[15px] py-[10px] md:px-[80px] md:py-[40px] text-center flex flex-col items-center justify-start gap-[14px]"
        >
          <p class="text-[32px] md:text-[55px] font-bold leading-[60px]">Set the mood</p>
          <p class="text-sm md:text-base">
            Curated playlists from Woody + Helena, plus some of our <br />
            friends and favorite brands.
          </p>
          <div class="px-[58px] py-[13px] bg-white text-black">Spotify</div>
        </div>
        <div
          class="bg-black/70 md:bg-black w-full flex flex-col gap-[15px] items-center justify-start py-[28px]"
        >
          <p>Follow us, share us, drink Ha(us)</p>
          <div class="flex gap-[21px]">
            <p class="linkP">Instagram</p>
            <p class="linkP">Twitter</p>
            <p class="linkP">Facebook</p>
          </div>
        </div>
      </div>
      <div
        class="bg-black/70 relative z-30 md:bg-black md:w-[40%] px-[15px] py-[10px] md:px-[80px] md:py-[40px] mx-auto text-center flex flex-col items-center justify-start"
      >
        <p class="text-[29px] mb-[22px]">Are you 21 or older?</p>
        <p class="text-lg mb-[31px]">You must be of legal drinking age to purchase Haus.</p>
        <input
          class="mb-[35px] bg-transparent border border-white px-[20px] py-[10px]"
          type="text"
        />
        <p class="">No, I’m not of drinking age</p>
      </div>
    </section>

    <hr class="mx-[81px] mb-[100px] mt-[100px] font-sans" />
    <section class="relative z-20 w-full">
      <iframe
        src="https://yandex.ru/map-widget/v1/?um=constructor%3Aafb093df40f3f1dd4c84b1777979602599b69918f7a6691bed0f47e814ec4bec&amp;source=constructor"
        width="100%"
        height="400"
        frameborder="0"
      ></iframe>
    </section>
    <hr class="mx-[81px] mb-[100px] mt-[100px] font-sans" />
  </div>
</template>

<script lang="ts">
export default {
  data() {
    return {
      banner: true,
      stick: false
    }
  },

  mounted() {
    window.addEventListener('scroll', this.handleScroll)
    // Получаем все элементы с классом .sticky-menu

    if (!this.banner) {
      this.stick = true
    }
  },
  beforeDestroy() {
    window.removeEventListener('scroll', this.handleScroll)
  },
  methods: {
    moveBackground(event: any) {
      // const image = this.$refs.image
      // const imageRect = image.getBoundingClientRect()
      // // Вычисляем центр изображения
      // const centerX = imageRect.left + imageRect.width / 1.2
      // const centerY = imageRect.top + imageRect.height / 1.2
      // // Вычисляем углы поворота в зависимости от положения курсора
      // const deltaX = event.clientX - centerX
      // const deltaY = event.clientY - centerY
      // const angleX = (deltaY / imageRect.height) * 8 // Управляйте углом поворота по оси X
      // const angleY = (deltaX / imageRect.width) * 8 // Управляйте углом поворота по оси Y
      // // Применяем поворот к изображению
      // image.style.transform = `rotateX(${angleX}deg) rotateY(${angleY}deg)`
    },
    handleScroll() {
      if (!this.banner || window.pageYOffset > 60) {
        this.stick = true
      } else {
        this.stick = false
      }
    }
  }
}
</script>

<style scoped>
.sticky-menu {
  top: 60px; /* Начальное положение ниже */
  transition: all 0.5s;
}

.sticky-menu.sticky {
  position: fixed;
  top: 0; /* Прилипает к верху экрана */
  width: 100%;
}
.linkP {
  position: relative;
  display: inline-block;

  text-decoration: none; /* Убираем стандартное подчеркивание */
}

.linkP::after {
  content: ''; /* Пустой контент для создания псевдоэлемента */
  position: absolute;
  bottom: -2px; /* Расположение подчеркивания снизу текста */
  left: 0;
  width: 0%; /* Начальная ширина подчеркивания */
  height: 2px; /* Толщина подчеркивания */
  background-color: white; /* Цвет подчеркивания */
  transition: width 0.3s; /* Плавная анимация изменения ширины */
}

.linkP:hover::after {
  width: 100%; /* Изменяем ширину подчеркивания при наведении */
}
input:focus {
  outline: none; /* Убираем стандартный контур фокуса */
  box-shadow: 0 0 0 2px white; /* Белая обводка при фокусировке */
}
.attach {
  background-attachment: fixed;
  background-repeat: no-repeat;
  background-size: cover;
}
</style>
