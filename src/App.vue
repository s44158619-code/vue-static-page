<template>
  <div class="min-h-screen flex flex-col items-center justify-center bg-gradient-to-b from-indigo-900 via-purple-900 to-black text-white relative overflow-hidden">
    <!-- 달 -->
    <div class="moon absolute top-20 right-32 w-40 h-40 bg-yellow-300 rounded-full shadow-[0_0_60px_rgba(255,255,180,0.8)] animate-pulse"></div>

    <!-- 구름 -->
    <div class="cloud cloud-1"></div>
    <div class="cloud cloud-2"></div>

    <!-- 제목 -->
    <h1 class="text-5xl md:text-6xl font-bold mb-4 text-center tracking-widest drop-shadow-lg animate-fade-in">
      🌕 풍요로운 한가위 🌾
    </h1>

    <!-- 인삿말 -->
    <p class="text-lg md:text-xl opacity-90 mb-8 text-center animate-fade-in-delay">
      가족과 함께하는 따뜻한 추석 보내세요 🍂
    </p>

    <!-- 버튼 -->
    <button
        class="bg-yellow-400 hover:bg-yellow-500 text-black font-semibold py-3 px-6 rounded-2xl shadow-md transition transform hover:-translate-y-1 animate-bounce-slow"
        @click="sayHello"
    >
      덕담 받기 🎁
    </button>

    <!-- 덕담 팝업 -->
    <transition name="fade">
      <div
          v-if="showWish"
          class="absolute bottom-20 bg-white/10 backdrop-blur-lg border border-white/30 text-yellow-200 py-4 px-6 rounded-xl shadow-lg animate-fade-in"
      >
        <p class="text-lg">“보름달처럼 마음도 풍성해지는 추석 되세요 🌝”</p>
      </div>
    </transition>
  </div>
</template>

<script lang="ts" setup>
import { ref } from 'vue'

const showWish = ref(false)

const sayHello = () => {
  showWish.value = true
  setTimeout(() => (showWish.value = false), 4000)
}
</script>

<style scoped>
@keyframes fade-in {
  0% { opacity: 0; transform: translateY(10px); }
  100% { opacity: 1; transform: translateY(0); }
}

.animate-fade-in {
  animation: fade-in 1s ease-out forwards;
}

.animate-fade-in-delay {
  animation: fade-in 1.5s ease-out forwards;
}

/* 구름 효과 */
.cloud {
  position: absolute;
  background: rgba(255, 255, 255, 0.2);
  border-radius: 50%;
  filter: blur(8px);
  animation: float 60s linear infinite;
}
.cloud::before,
.cloud::after {
  content: '';
  position: absolute;
  background: inherit;
  border-radius: 50%;
}
.cloud-1 {
  width: 200px;
  height: 60px;
  top: 150px;
  left: -200px;
  animation-delay: 0s;
}
.cloud-1::before {
  width: 100px;
  height: 100px;
  top: -20px;
  left: 50px;
}
.cloud-2 {
  width: 250px;
  height: 80px;
  top: 300px;
  left: -300px;
  animation-delay: 10s;
}
.cloud-2::before {
  width: 120px;
  height: 120px;
  top: -10px;
  left: 70px;
}

@keyframes float {
  from { transform: translateX(0); }
  to { transform: translateX(2000px); }
}

.animate-bounce-slow {
  animation: bounce 3s infinite;
}

@keyframes bounce {
  0%, 100% { transform: translateY(0); }
  50% { transform: translateY(-8px); }
}

/* fade transition */
.fade-enter-active, .fade-leave-active {
  transition: opacity 0.5s;
}
.fade-enter-from, .fade-leave-to {
  opacity: 0;
}
</style>
