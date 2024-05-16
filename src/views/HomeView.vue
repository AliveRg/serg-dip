<script setup lang="ts">
import { defineComponent } from 'vue'
import FormComponent from '@/components/FormComponent.vue'
import 'intersection-observer'
</script>

<template>
  <main>
    <FormComponent
      :isAnimationActive.sync="active"
      :triggerMethod.sync="triggerMethod"
      :nameForm="nameForm"
      @some-event="toggleAnimation('')"
    />
    <section
      class="section-1 grid grid-cols-1 md:grid-cols-2 relative z-0 bg-[#996B60]"
      @mouseover="startAnimation"
    >
      <div class="w-full h-screen relative">
        <img src="@/assets/head1.png" alt="" class="absolute top-0 left-0 w-full h-full" />
      </div>
      <div
        class="w-full flex flex-col items-start justify-end gap-[50px] px-[13px] md:px-[60px] pb-[30px] md:pb-[100px] text-white"
      >
        <p
          class="text-[43px] font-normal font-sans leading-[96px] opacity-0"
          :class="{ 'animate-slide-down': showButton }"
        >
          Концертный прокат и обзоры инструментов
        </p>
        <p
          class="text-lg font-normal font-sans leading-loose opacity-0"
          :class="{ 'animate-slide-up': showButton }"
        >
          Веберете то, что подходит именно вам. Разберитесь в структуре и назначении инструментов!
        </p>
        <div class="relative">
          <RouterLink
            to="/catalog"
            class="opacity-0 border border-white px-[52px] py-[19px] text-xs font-normal font-sans uppercase leading-[14px] tracking-wide transition-all hover:text-black hover:bg-white"
            :class="{ 'animate-fade-in': showButton }"
          >
            Смотреть каталог
          </RouterLink>
        </div>
      </div>
    </section>
    <section
      class="section-2 container relative z-20 target-element grid grid-cols-1 md:grid-cols-3 gap-[50px] md:gap-0 items-start mt-[60px] mx-auto justify-between text-center text-black text-lg font-sans font-normal transition-all duration-700"
      :class="interTarget ? 'opacity-1' : 'opacity-0  translate-y-[10%]'"
    >
      <div class="flex flex-col items-center justify-start gap-[36px] mx-auto">
        <p>"Лексланд, небольшое производство качественных синтезаторов"</p>
        <img src="@/assets/logoStud1.png" alt="" class="w-[300px] h-[150px] object-cover" />
      </div>
      <div class="flex flex-col items-center justify-start gap-[36px] mx-auto">
        <p>
          “THEFrost. предоставляют возможность через нас узнать из знаменитые электро-гитары
          поближе.”
        </p>
        <img src="@/assets/logoStud2.png" alt="" class="w-[300px] h-[150px] object-cover" />
      </div>
      <div class="flex flex-col items-center justify-start gap-[36px] mx-auto">
        <p>
          “Burnabee, слушайте подкасты от наших друзей и узнаваейте новости в мире музыки первыми”
        </p>
        <img src="@/assets/logoStud3.png" alt="" class="w-[300px] h-[150px] object-cover" />
      </div>
    </section>
    <hr class="mx-[81px] mb-[100px] mt-[41px] font-sans" />
    <section
      class="section-3 relative z-20 container text-center text-black font-normal font-sans flex flex-col items-center justify-start gap-[80px] mx-auto"
    >
      <h3 class="flex flex-col items-center justify-start gap-[24px]">
        <p class="text-[64px]">
          Мы не создаем, <br />
          но создаете вы
        </p>
        <p><span class="font-bold">Не</span> унылые курсы</p>
      </h3>
      <div
        class="flex flex-col md:flex-row items-start justify-between gap-[55px] text-center text-black font-normal font-sans"
      >
        <div
          v-for="item in impLink"
          :key="item.id"
          class="flex flex-col items-center justify-start gap-[19px] max-w-[382px] transition-all duration-700"
        >
          <div class="relative" v-if="item.img">
            <div class="absolute"></div>
            <img
              :src="`../../src/assets/${item.img}`"
              alt=""
              class="w-full md:min-w-[225px] rounded-se-[50px] rounded-es-[50px] md:rounded-se-[100px] md:rounded-es-[100px] lg:rounded-se-[150px] lg:rounded-es-[150px]"
            />
          </div>
          <div class="flex flex-col items-center justify-start">
            <p class="mb-[16px] text-3xl leading-[44px]">{{ item.name }}</p>
            <p class="mb-[25px] text-sm leading-7">
              {{ item.desription }}
            </p>
            <div
              class="px-[48px] py-[19px] bg-black text-white"
              @click="toggleAnimation(item.name)"
            >
              <div class="">Записаться сейчас</div>
            </div>
          </div>
        </div>
      </div>
    </section>
    <hr class="mx-[81px] mb-[100px] mt-[100px] font-sans" />

    <section class="relative z-20 section-4 container mx-auto flex flex-col gap-[50px]">
      <div class="w-full h-[550px] attach bg-[url('@/assets/attach.png')]"></div>
      <div
        class="flex flex-col md:flex-row justify-between items-center font-normal font-sans text-black"
      >
        <p class="text-[53px] leading-[80px]">От нового до Новейшего</p>
        <p class="leading-loose text-lg max-w-[538px]">
          При прокате инструментов появляется множество плюсов, от простого обновления оборудования,
          до низких затрат на начальном этапе.
          <br />
          (Единственный минус - красиво не разбить гитару об сцену, просьба так не делать)
        </p>
      </div>
    </section>
    <hr class="mx-[81px] mb-[100px] mt-[100px] font-sans" />

    <section class="relative z-20 section-4 container mx-auto flex flex-col sm:flex-row gap-[50px]">
      <div
        class="flex flex-col justify-end items-center gap-[21px] font-normal font-sans text-black max-w-[385px] px-[13px] sm:px-0"
      >
        <div class="flex flex-col justify-end items-start gap-[19px]">
          <p class="text-[30px] leading-[50px] md:leading-[80px]">Узнай что тебе нужно</p>
          <p class="leading-loose text-[18px] max-w-[538px]">
            Наши консультанты помогут с выбором подходяших гитар, устанвок и прочего, вникнув в вашу
            проблему.
          </p>
        </div>
        <div class="flex flex-col justify-end items-start gap-[19px]">
          <p class="text-[30px] leading-[50px] md:leading-[40px]">Нет затрат. Нет проблем.</p>
          <p class="leading-loose text-[18px] max-w-[538px]">
            При покупке инстументов, вы тратите большую часть капитала на оборудование, которое
            через время устареет. Потрать этот бюджет на рекламу!
          </p>
        </div>
        <div class="flex flex-col justify-end items-start gap-[19px]">
          <p class="text-[30px] leading-[50px] md:leading-[80px]">Онлайн обзор</p>
          <p class="leading-loose text-[18px] max-w-[538px]">
            Забронируй личную онлайн встречу в удобную дату и не трать время. По видео связи мы
            расскажем все, что ты хочешь и должен знать.
          </p>
        </div>
      </div>
      <div class="w-full h-[550px] attach bg-[url('@/assets/attach2.png')] sticky top-0"></div>
    </section>
    <section class="section-6 relative z-20 bg-black w-full mt-[45px] mb-[60px]">
      <div
        class="container flex flex-col md:flex-row gap-[50px] md:gap-0 items-center justify-between py-[50px] mx-auto"
      >
        <div
          v-for="ord in order"
          :key="ord.id"
          class="flex flex-col justify-center items-start gap-[20px] px-[15px] pb-[31px] text-white font-sans text-center max-w-[300px]"
        >
          <div class="w-full flex items-center justify-center gap-[4px]">
            <svg
              v-for="item in ord.stars"
              :key="item"
              width="20"
              height="20"
              viewBox="0 0 20 20"
              fill="none"
              xmlns="http://www.w3.org/2000/svg"
            >
              <g clip-path="url(#clip0_40_1278)">
                <path
                  d="M9.79336 0.636505C9.80745 0.592692 9.83507 0.554479 9.87227 0.527371C9.90946 0.500263 9.95429 0.485657 10.0003 0.485657C10.0463 0.485657 10.0912 0.500263 10.1284 0.527371C10.1656 0.554479 10.1932 0.592692 10.2073 0.636505L12.3925 7.35998C12.4066 7.40358 12.4341 7.4416 12.4711 7.46862C12.5082 7.49563 12.5528 7.51026 12.5986 7.51042H19.6681C19.7143 7.51003 19.7594 7.52435 19.7969 7.55129C19.8343 7.57824 19.8623 7.61641 19.8766 7.66029C19.8909 7.70417 19.8909 7.75147 19.8766 7.79535C19.8623 7.83922 19.8343 7.87739 19.7968 7.90433L14.0768 12.06C14.0397 12.0871 14.0122 12.1253 13.9981 12.169C13.9841 12.2127 13.9842 12.2598 13.9986 12.3035L16.1829 19.0269C16.1973 19.0707 16.1975 19.1178 16.1833 19.1616C16.1692 19.2055 16.1415 19.2437 16.1043 19.2707C16.0671 19.2978 16.0222 19.3124 15.9762 19.3123C15.9301 19.3123 15.8853 19.2976 15.8481 19.2704L10.1281 15.1139C10.091 15.0869 10.0462 15.0723 10.0003 15.0723C9.95439 15.0723 9.90964 15.0869 9.87249 15.1139L4.15249 19.2704C4.11533 19.2976 4.0705 19.3123 4.02446 19.3123C3.97843 19.3124 3.93356 19.2978 3.89633 19.2707C3.8591 19.2437 3.83143 19.2055 3.8173 19.1616C3.80317 19.1178 3.80331 19.0707 3.81771 19.0269L6.00292 12.3026C6.01719 12.2589 6.01722 12.2117 6.003 12.168C5.98878 12.1242 5.96105 12.0861 5.92379 12.0591L0.203793 7.90433C0.166372 7.87743 0.138467 7.83934 0.124106 7.79555C0.109745 7.75176 0.109672 7.70454 0.123896 7.66071C0.13812 7.61687 0.165907 7.57869 0.203243 7.55168C0.24058 7.52467 0.285536 7.51022 0.331619 7.51042H7.40118C7.44715 7.51045 7.49195 7.4959 7.52914 7.46887C7.56632 7.44184 7.59398 7.40372 7.60814 7.35998L9.79336 0.636505Z"
                  fill="#D9D9D9"
                />
              </g>
              <defs>
                <clipPath id="clip0_40_1278">
                  <rect width="20" height="20" fill="white" />
                </clipPath>
              </defs>
            </svg>
          </div>
          <p class="w-full text-lg leading-loose">
            {{ ord.content }}
          </p>
          <p class="w-full uppercase text-sm leading-loose">— {{ ord.name }}</p>
          <p class="w-full text-zinc-500 text-base capitalize">{{ ord.status }}</p>
        </div>
      </div>
    </section>
    <section class="relative z-20 section_3">
      <div class="mx-auto px-8">
        <div class="section_3_werapper group">
          <div class="title_section_3">
            <p>Гитарный кабинет</p>
          </div>
          <div class="imfo_section_3 flex flex-col md:flex-row">
            <div class="info_inner_left-section_3">
              <div
                class="left_section_3-wrapper md:group-hover:translate-x-0 md:opacity-0 md:group-hover:opacity-[1] md:-translate-x-[10%] transition-all delay-200 duration-500"
              >
                <div class="section_3_inner-up">
                  <div class="section_3_inner-up-title">
                    <img src="@/assets/Time.svg" alt="" />
                    <p>Быстрое подключение</p>
                  </div>
                </div>
                <div class="section_3_inner-under">
                  <p>
                    Подключайте кабинет к любым гитарам так же просто, как подключаете зарядку к
                    телефону
                  </p>
                </div>
              </div>
              <div
                class="right_section_3-wrapper md:group-hover:translate-x-0 md:opacity-0 md:group-hover:opacity-[1] md:-translate-x-[10%] transition-all delay-[400] duration-500"
              >
                <div class="section_3_inner-up">
                  <div class="section_3_inner-up-title">
                    <img src="@/assets/Sun.svg" alt="" />
                    <p>Как на счет звука?</p>
                  </div>
                </div>
                <div class="section_3_inner-under">
                  <p>Marshal идеально подходит для ценителей идеального звечания</p>
                </div>
              </div>
            </div>
            <div class="info_inner_center-section_3">
              <img src="@/assets/cabinet.webp" alt="" />
            </div>
            <div class="info_inner_right-section_3">
              <div
                class="right_section_3-wrapper md:group-hover:translate-x-0 md:opacity-0 md:group-hover:opacity-[1] md:translate-x-[10%] transition-all delay-200 duration-500"
              >
                <div class="section_3_inner-up">
                  <div class="section_3_inner-up-title">
                    <img src="@/assets/Arrows.svg" alt="" />
                    <p>Соеденяйте настраивайте</p>
                  </div>
                </div>
                <div class="section_3_inner-under">
                  <p>Подключение нескольких кабинетов происходит с помощью всего одного провода!</p>
                </div>
              </div>
              <div
                class="right_section_3-wrapper md:group-hover:translate-x-0 md:opacity-0 md:group-hover:opacity-[1] md:translate-x-[10%] transition-all delay-[400] duration-500"
              >
                <div class="section_3_inner-up">
                  <div class="section_3_inner-up-title">
                    <img src="@/assets/Infinity.svg" alt="" />
                    <p>Невероятная мощность</p>
                  </div>
                </div>
                <div class="section_3_inner-under">
                  <p>Встроенные 4 динамика диаметром 12" и частотой в пределах 20 - 20000Гц</p>
                </div>
              </div>
            </div>
          </div>
        </div>
      </div>
    </section>
    <section
      class="section-7 container mx-auto mb-[60px] relative z-20 flex flex-col md:flex-row items-center justify-between gap-[50px] md:gap-[100px]"
    >
      <div
        class="w-full h-[330px] md:h-[550px] attach bg-[url('@/assets/attach3.png')] top-0 rounded-t-[0px] hover:rounded-t-[150px] transition-all"
      ></div>
      <div
        class="flex flex-col justify-between content-between md:h-[550px] px-[13px] sm:px-0 text-black font-sans md:max-w-[30%]"
      >
        <p class="text-[22px] md:text-[32px]">"Да хоть диджей!"</p>
        <div class="flex flex-col gap-[20px]">
          <p class="text-sm md:text-md">
            Производство студийных, тренировочных и много каких пультов. Диджей? Звуковик? Просто
            интересующейся? Поможем в выборе обьясним, что да как. Ты только не паникуй)
          </p>
          <a href="" class="text-xs md:text-sm">Записаться</a>
        </div>
      </div>
    </section>
  </main>
</template>

<script lang="ts">
export default defineComponent({
  data() {
    return {
      nameForm: '',
      triggerMethod: false,
      active: false,
      showButton: false,
      observer: null as IntersectionObserver | null, // Инициализируем свойство как null или IntersectionObserver
      interTarget: false,
      impLink: [
        {
          id: 1,
          name: 'Стартовые знания',
          desription:
            'Создание продакшена, кооперация и релизы, узнайте обо всем этом на нашем курсе!',
          img: 'prew1.png',
          link: '#',
          imgBest: false,
          styles: {
            isVisible: false // Добавьте свойство для хранения видимости элемента
          }
        },
        {
          id: 2,
          name: 'Необычные данные',
          desription:
            'Думать что знаешь много = не знать большую часть. Пойми, что тебя ждет и научись строить планы',
          img: 'prew2.png',
          link: '#',
          imgBest: true,
          styles: {
            isVisible: false // Добавьте свойство для хранения видимости элемента
          }
        },
        {
          id: 3,
          name: 'Музыка дела',
          desription:
            'Продвижение групп и компаний в музыкальной сфере, на что обращать внимание и действие!',
          img: 'prew3.png',
          link: '#',
          imgBest: true,
          styles: {
            isVisible: false // Добавьте свойство для хранения видимости элемента
          }
        }
      ],
      order: [
        {
          id: 1,
          content:
            '“Получил массу преимуществ, спасибо консультанту Сергую за подробную консультацию!”',
          name: 'Susan',
          status: 'Анонимный отзыв',
          stars: 5
        },
        {
          id: 2,
          content:
            '“Мне нравится эта новая концепция, выступаем на прокатном оборудовании и продолжим, удобно и без рисков - все на страховке :)”',
          name: 'Культет',
          status: 'Частный отзыв',
          stars: 5
        },
        {
          id: 3,
          content:
            '“Курс для начального уровня просто великолепен, получил сжатые данные, саму суть. Как стартовать и где искать коопераций! Спасибо куратору Андрею!”',
          name: 'Ликленд',
          status: 'Частный отзыв',
          stars: 5
        }
      ]
    }
  },
  components: {
    FormComponent
  },
  created() {
    // В методе created() ничего не делаем, так как IntersectionObserver должен быть инициализирован после монтирования компонента
  },
  mounted() {
    window.addEventListener('scroll', this.handleScroll)
    // Получаем все элементы с классом .sticky-menu

    this.observer = new IntersectionObserver(this.handleIntersect, {
      // Параметры конфигурации IntersectionObserver, если необходимо
    })

    // Получите ссылки на элементы, которые вы хотите отслеживать
    const targets = document.querySelectorAll('.target-element')

    // Начните отслеживание каждого целевого элемента
    targets.forEach((target) => {
      if (this.observer) {
        this.observer.observe(target)
      }
    })
  },
  beforeUnmount() {
    // Метод beforeUnmount() вместо beforeDestroy()
    if (this.observer) {
      this.observer.disconnect()
    }
    window.removeEventListener('scroll', this.handleScroll)
  },
  methods: {
    toggleAnimation(name: any) {
      // Вызываем метод verselMethod() в дочернем компоненте
      this.active = !this.active
      this.triggerMethod = !this.triggerMethod
      this.nameForm = name
    },
    startAnimation() {
      this.showButton = true
    },
    handleScroll() {
      if (window.pageYOffset > 60) {
        this.showButton = true
      }
    },
    handleIntersect(entries: IntersectionObserverEntry[], observer: IntersectionObserver) {
      entries.forEach((entry, index) => {
        if (entry.isIntersecting) {
          // Элемент виден
          this.interTarget = true
          this.impLink[index].styles.isVisible = true
          console.log(`Element ${index} is visible`)
        } else {
          // Элемент не виден
          this.interTarget = false
          this.impLink[index].styles.isVisible = false
          console.log(`Element ${index} is not visible`)
        }
      })
      entries.forEach((entry) => {
        if (entry.isIntersecting) {
          // Элемент виден
          this.interTarget = true
          console.log('Element is visible')
        } else {
          // Элемент не виден
          this.interTarget = false

          console.log('Element is not visible')
        }
      })
    }
  }
})
</script>

<style scoped>
.section_3 {
  margin: 150px 0;
}
.container {
}
.section_3_werapper {
  display: flex;
  flex-direction: column;
  align-items: center;
}
.title_section_3 {
  font-size: 59px;
  margin-bottom: 80px;
  color: #343339d7;
  font-family: 'Mulish-VariableFont', sans-serif;
}
.imfo_section_3 {
  width: 100%;
  display: flex;
  align-items: center;
  justify-content: space-between;
  font-family: 'Mulish-Italic', sans-serif;
}
.info_inner_left-section_3 {
  display: flex;
  flex-direction: column;
  align-items: start;
  gap: 80px;
}
.left_section_3-wrapper {
  display: flex;
  flex-direction: column;
  align-items: start;
  gap: 20px;
  max-width: 370px;
}
.section_3_inner-up {
}
.section_3_inner-up-title {
  font-size: 35px;
  display: flex;
  align-items: center;
  justify-content: start;
  gap: 21px;
  color: #343339;
}

.section_3_inner-under {
  font-size: 19px;
  color: #4e5659;
}
.right_section_3-wrapper {
  display: flex;
  flex-direction: column;
  align-items: start;
  gap: 20px;
  max-width: 370px;
}
.info_inner_center-section_3 {
}
.info_inner_right-section_3 {
  display: flex;
  flex-direction: column;
  align-items: start;
  gap: 80px;
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
@keyframes slide-up {
  0% {
    opacity: 0;
    transform: translateY(50px);
  }
  100% {
    opacity: 1;
    transform: translateY(0);
  }
}

@keyframes slide-down {
  0% {
    opacity: 0;
    transform: translateY(-50px);
  }
  100% {
    opacity: 1;
    transform: translateY(0);
  }
}

@keyframes fade-in {
  0% {
    opacity: 0;
  }
  100% {
    opacity: 1;
  }
}

.animate-slide-up {
  animation: slide-up 0.5s ease forwards;
}

.animate-slide-down {
  animation: slide-down 0.9s ease forwards;
}

.animate-fade-in {
  animation: fade-in 1s ease forwards;
}
</style>
