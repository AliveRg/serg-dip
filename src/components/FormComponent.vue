<script lang="ts" setup>
import { defineComponent } from 'vue'
</script>
<template>
  <div class="" v-if="isAnimationActive && triggerMethod">
    <div
      v-if="closebtn"
      class="fixed top-0 right-0 bg-white p-[20px] m-[20px] z-[70] rounded-full"
      @click.stop="verselMethod(), (closebtn = false)"
    >
      <svg
        class="w-6 h-6 text-gray-800 dark:text-white"
        aria-hidden="true"
        xmlns="http://www.w3.org/2000/svg"
        width="24"
        height="24"
        fill="none"
        viewBox="0 0 24 24"
      >
        <path
          stroke="currentColor"
          stroke-linecap="round"
          stroke-linejoin="round"
          stroke-width="2"
          d="M6 18 17.94 6M18 18 6.06 6"
        />
      </svg>
    </div>
    <div
      class="fixed top-0 left-0 w-screen h-screen bg-black/70 z-[40] group"
      @click.self="verselMethod()"
    >
      <Transition mode="out-in">
        <div
          v-if="verselNew"
          class="fixed h-[500px] w-[300px] top-1/2 left-1/2 -translate-x-1/2 -translate-y-1/2 grid grid-cols-3 grid-rows-3 z-[50] transition-all"
          :class="verselLast ? 'overflow-hidden rounded-[10px]' : ''"
        >
          <div
            class="w-full h-full bg-white transition-all duration-500"
            :class="
              versel
                ? 'scale-[100%]  rounded-none translate-x-0 translate-y-0 opacity-[1]'
                : '-translate-x-[40%] rounded-[15px] -translate-y-[10%] scale-[90%] opacity-0'
            "
          ></div>
          <div
            class="w-full h-full bg-white transition-all duration-500"
            :class="
              versel
                ? 'scale-[100%]  rounded-none translate-x-0 translate-y-0 opacity-[1]'
                : ' rounded-[15px] -translate-y-[40%] scale-[90%] opacity-0'
            "
          ></div>
          <div
            class="w-full h-full bg-white transition-all duration-500"
            :class="
              versel
                ? 'scale-[100%]  rounded-none translate-x-0 translate-y-0 opacity-[1]'
                : ' rounded-[15px] translate-x-[40%] -translate-y-[10%] scale-[90%] opacity-0'
            "
          ></div>

          <div
            class="w-full h-full bg-white transition-all duration-500"
            :class="
              versel
                ? 'scale-[100%]  rounded-none translate-x-0 translate-y-0 opacity-[1]'
                : ' rounded-[15px] -translate-x-[60%] scale-[90%] opacity-0'
            "
          ></div>
          <div
            class="w-full h-full bg-white transition-all duration-500"
            :class="
              versel
                ? ' scale-[100%]  rounded-none translate-y-0 opacity-[1]'
                : 'scale-[110%] rounded-[15px]  opacity-0'
            "
          ></div>
          <div
            class="w-full h-full bg-white transition-all duration-500"
            :class="
              versel
                ? 'scale-[100%]  rounded-none translate-x-0 translate-y-0 opacity-[1]'
                : ' rounded-[15px] translate-x-[60%] scale-[90%] opacity-0'
            "
          ></div>

          <div
            class="w-full h-full bg-white transition-all duration-500"
            :class="
              versel
                ? 'scale-[100%]  rounded-none translate-x-0 translate-y-0 opacity-[1]'
                : ' rounded-[15px]  -translate-x-[50%] translate-y-[10%] scale-[90%] opacity-0'
            "
          ></div>
          <div
            class="w-full h-full bg-white transition-all duration-500"
            :class="
              versel
                ? 'scale-[100%]  rounded-none translate-x-0 translate-y-0 opacity-[1]'
                : ' rounded-[15px] translate-y-[40%] scale-[90%] opacity-0'
            "
          ></div>
          <div
            class="w-full h-full bg-white transition-all duration-500"
            :class="
              versel
                ? 'scale-[100%]  rounded-none translate-x-0 translate-y-0 opacity-[1]'
                : ' rounded-[15px] translate-x-[50%] translate-y-[10%] scale-[90%] opacity-0'
            "
          ></div>
        </div>
      </Transition>
      <Transition name="fade" mode="out-in">
        <div
          v-if="verselLast"
          class="fixed h-[500px] w-[300px] bg-white top-1/2 left-1/2 -translate-x-1/2 -translate-y-1/2 transition-all duration-500 z-[60] rounded-[10px]"
        >
          <div class="w-full p-[10px] font-sans text-[#4f4f4f] h-[70%]">
            <h2 class="text-2xl font-semibold text-gray-800 mb-4">{{ nameForm }}</h2>
            <form @submit.prevent="submitForm" class="flex flex-col justify-between h-full">
              <div class="">
                <div class="mb-4">
                  <label for="name" class="block text-sm font-medium text-gray-700">Имя</label>
                  <input
                    type="text"
                    id="name"
                    v-model="formData.name"
                    placeholder="Введите ваше имя"
                    class="mt-1 block w-full border-gray-300 rounded-md shadow-sm focus:border-blue-300 focus:ring focus:ring-blue-200 focus:ring-opacity-50"
                  />
                </div>
                <div class="mb-4">
                  <label for="surname" class="block text-sm font-medium text-gray-700"
                    >Фамилия</label
                  >
                  <input
                    type="text"
                    id="surname"
                    v-model="formData.surname"
                    placeholder="Введите вашу фамилию"
                    class="mt-1 block w-full border-gray-300 rounded-md shadow-sm focus:border-blue-300 focus:ring focus:ring-blue-200 focus:ring-opacity-50"
                  />
                </div>
                <div class="mb-4">
                  <label for="phone" class="block text-sm font-medium text-gray-700"
                    >Номер телефона</label
                  >
                  <input
                    type="tel"
                    id="phone"
                    v-model="formData.phone"
                    placeholder="Введите номер телефона"
                    class="mt-1 block w-full border-gray-300 rounded-md shadow-sm focus:border-blue-300 focus:ring focus:ring-blue-200 focus:ring-opacity-50"
                  />
                </div>
              </div>
              <div class="mb-4">
                <label class="flex items-center">
                  <input type="checkbox" v-model="formData.agreed" class="form-checkbox" />
                  <span class="ml-2 text-sm text-gray-700"
                    >Согласен с условиями обработки данных</span
                  >
                </label>
              </div>
              <button
                @click.self="verselMethod()"
                type="submit"
                :disabled="
                  !formData.agreed || !formData.name || !formData.surname || !formData.phone
                "
                class="w-full py-2 px-4 bg-blue-600 text-white font-semibold rounded-md hover:bg-blue-700 focus:outline-none focus:bg-blue-700"
              >
                Отправить
              </button>
            </form>
          </div>
        </div>
      </Transition>
    </div>
  </div>
</template>

<script lang="ts">
export default defineComponent({
  data() {
    return {
      closebtn: true,
      verselNew: false,
      versel: false,
      verselLast: false,
      formData: {
        name: '',
        surname: '',
        phone: '',
        agreed: false
      }
    }
  },
  methods: {
    submitForm() {
      // Обработка отправки формы
      console.log('Отправка формы', this.formData)
    },
    verselMethod() {
      if (this.verselNew) {
        setTimeout(() => {
          this.versel = false
        }, 600)
        setTimeout(() => {
          this.verselLast = false
        }, 200)
        setTimeout(() => {
          this.verselNew = false
        }, 1100)
        setTimeout(() => {
          this.$emit('someEvent')
          console.log('true')
        }, 1400)
      } else {
        this.verselNew = true
        setTimeout(() => {
          this.verselLast = true
        }, 500)
        if (this.verselNew) {
          setTimeout(() => {
            this.versel = true
          }, 100)
        }
        console.log('false')
      }
    }
  },
  watch: {
    triggerMethod(oldValue, newValue) {
      // Вызываем метод verselMethod() при изменении значения triggerMethod
      if (!newValue) {
        this.verselMethod()
        this.closebtn = true
      }
    }
  },
  props: {
    isAnimationActive: { type: Boolean, default: false },
    triggerMethod: { type: Boolean, default: false },
    nameForm: String
  }
})
</script>

<style scoped>
.v-enter-active,
.v-leave-active {
  transition: opacity 0s ease;
}

.v-enter-from,
.v-leave-to {
  opacity: 0;
}
.fade-enter-active,
.fade-leave-active {
  transition: opacity 0.5s ease;
  -webkit-box-shadow: -9px -23px 73px 12px rgba(255, 255, 255, 1);
  -moz-box-shadow: -9px -23px 73px 12px rgba(255, 255, 255, 1);
  box-shadow: -9px -23px 73px 12px rgba(255, 255, 255, 1);
}

.fade-enter-from,
.fade-leave-to {
  opacity: 0;
}
</style>
