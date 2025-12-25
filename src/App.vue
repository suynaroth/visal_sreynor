<script setup>
import { RouterLink, RouterView } from 'vue-router'
import HelloWorld from './components/HelloWorld.vue'
</script>

<template>
  <div id="app">
    <!-- Landing Section -->
    <section v-if="!opened" class="landing">
      <div
        class="min-h-screen w-full flex flex-col justify-start items-center bg-linear-to-br from-purple-500 via-pink-500 to-red-500 px-4">
        <!-- Video element -->
        <!-- <video autoplay muted playsinline class="absolute top-0 left-0 w-full h-full object-cover">
          <source src="/images/vdo.mp4" type="video/mp4">
        </video> -->

        <!-- Photo background -->
        <img src="/images/landing-bg.jpg" alt="Background" class="absolute inset-0 w-full h-full object-cover" />

        <!-- Overlay -->
        <div class="absolute inset-0 bg-black opacity-30"></div>

        <div class="relative z-10 flex flex-col justify-center pt-40 items-center text-center">
          <h1 class="text-3xl md:text-5xl font-moul leading-relaxed lg:text-6xl mb-4 text-pink-400 text-center">
            សិរីមង្គលអាពាហ៍ពិពាហ៍
          </h1>
          <p class="text-lg md:text-xl lg:text-2xl mb-8 text-white text-center max-w-md">
            The Wedding Day
          </p>
          <img src="/images/mark-png-pink.svg" alt="Ornament" class="w-66 mb-8" />
          <h3 class="text-xl md:text-xl font-moul leading-relaxed lg:text-6xl mb-4 text-pink-400 text-center">
            សូមគោរពអញ្ជើញ
          </h3>
          <p class="text-lg md:text-xl font-moul lg:text-2xl mb-8 text-white text-center max-w-md">
            {{ questName }}
          </p>
          <button
            class="bg-white text-pink-600 font-nokora px-8 py-3 md:px-10 md:py-4 rounded-full hover:bg-pink-50 hover:scale-105 transition-all duration-300 font-semibold text-lg shadow-lg"
            @click="openInvitation">
            បើកធៀប
          </button>
        </div>
      </div>
      <!-- <button class="text-pink" @click="openInvitation">Click to Open</button> -->
    </section>

    <!-- STORY SPLASH -->
    <transition name="fade">
      <section v-if="opened && step === 1" class="story-screen">
        <div
          class="min-h-screen w-full flex flex-col justify-end items-center bg-linear-to-br from-purple-500 via-pink-500 to-red-500 px-4">
          <!-- Photo background -->
          <img src="/images/ld-bg.jpg" class="absolute inset-0 w-full h-full object-cover" />
          <div class="story-text relative z-10 flex flex-col justify-center items-center mb-10 text-center px-4">
            <p class="text-black">{{ displayedText }}</p>
          </div>
        </div>
      </section>
    </transition>

    <!-- Main Invitation -->
    <section v-if="opened && step === 2" class="invitation">
      <div
        class="min-h-screen w-full flex flex-col justify-start items-center bg-linear-to-br from-purple-500 via-pink-500 to-red-500 px-4">
        <!-- Photo background -->
        <img src="/images/bg-gate.jpg" alt="Background"
          class="absolute inset-0 w-full h-full object-cover fixed no-repeat" />

        <!-- Overlay -->
        <!-- <div class="absolute inset-0 bg-black opacity-30"></div> -->

        <div class="relative z-10 flex flex-col justify-center pt-40 items-center text-center">
          <h1 class="text-2xl md:text-2xl font-moul leading-relaxed lg:text-4xl mb-4 text-pink-400 text-center">
            សិរីមង្គលអាពាហ៍ពិពាហ៍
          </h1>
          <p class="text-lg md:text-xl lg:text-2xl mb-8 text-white text-center max-w-md">
            The Wedding Day
          </p>
          <!-- <img src="/images/mark-png-pink.svg" alt="Ornament" class="w-66 mb-8" /> -->
          <div class="grid grid-cols-2 gap-8 font-moul leading-relaxed mb-4 text-white text-center max-w-md">
            <div class="grid grid-rows-2 gap-2">
              <p>លោក សុខ សប្បាយ</p>
              <p>អ្នកស្រី ឡុង ដានី</p>
            </div>
            <div class="grid grid-rows-2 gap-2">
              <p>លោក សេង ពិសាល</p>
              <p>អ្នកស្រី​ នូ រ៉ានី</p>
            </div>
          </div>

          <div
            class="backdrop-blur-xs bg-white/15 rounded-3xl p-8 flex flex-col items-center text-center max-w-3xl shadow-xl">
            <h3 class="text-lg md:text-lg font-moul leading-relaxed lg:text-xl mb-4 text-pink-400 text-center">
              មានកិត្តិយសសូមគោរពអញ្ជើញ
            </h3>
            <p class="text-white font-metal leading-loose mb-4">
              ឯកឧត្តម លោកឧកញ៉ា លោកជំទាវ លោក លោកស្រី អ្នកនាង កញ្ញា អញ្ជើញចូលរួមជាអធិបតី
              និងជាភ្ញៀវកិត្តិយសបើម្បីប្រសិទ្ធិពរជ័យ សិរីសួស្តីជ័យមង្គលក្នុងកម្មវិធីរៀបមង្គលអាពាហ៍ពិពាហ៍
              កូនប្រុស​-​កូនស្រី របស់យើងខ្ញុំ
            </p>
            <h2
              class="text-3xl md:text-4xl font-moul leading-relaxed lg:text-5xl mb-4 text-pink-300 text-center flex items-center justify-center gap-2">
              វិសាល
              <img src="/images/logo.jpg" alt="Logo" class="w-10 h-10" />
              ស្រីណូ
            </h2>

            <p class="text-white font-metal leading-loose mb-4">
              ដែលនឹងប្រព្រឹត្តទៅនៅថ្ងៃសុក្រ ៤រោច ខែមាឃ ឆ្នាំម្សាញ់ សប្តស័ក ពុទ្ធសករាជ ២៥៦៩ ត្រូវនឹងថ្ងៃទី ០៦ ខែកុម្ភៈ
              ឆ្នាំ ២០២៦
            </p>
            <p class="text-white font-metal leading-loose mb-4">
              វេលាម៉ោង ៤: 00 រសៀល ​ស្ថិតនៅគេហដ្ឋានខាងស្រី ភូមិដង្កៀបក្តាម ឃុំពាមបន្ទារ ស្រុកកំពង់ត្របែក ខេត្តព្រៃវែង។
              ដោយមេត្រីភាព!
            </p>

            <div class="mt-6">
              <RouterLink to="/main-event"
                class="bg-pink-600 text-white font-nokora px-6 py-2 md:px-8 md:py-3 rounded-full hover:bg-pink-700 hover:scale-105 transition-all duration-300 font-semibold text-lg shadow-lg">
                ព័ត៌មានលម្អិតពិធីមង្គលការ
              </RouterLink>
            </div>
          </div>
        </div>
      </div>
    </section>
    
  </div>
</template>

<script>
export default {
  data() {
    return {
      opened: false,
      questName: '',
      step: 1,
      storyTexts: [
        "Once upon a time, in a land far away...",
        "There lived a brave knight and a beautiful princess...",
        "Their love story was filled with adventures and magic...",
        "And they lived happily ever after."
      ],
      displayedText: '',
    }
  },
  mounted() {
    const urlParams = new URLSearchParams(window.location.search)
    const nameParam = urlParams.get('name')
    if (nameParam) {
      this.questName = decodeURIComponent(nameParam)
    }
  },
  methods: {
    openInvitation() {
      this.opened = true

      //typing effect for story texts
      let currentTextIndex = 0
      const typeNextText = () => {
        if (currentTextIndex < this.storyTexts.length) {
          const fullText = this.storyTexts[currentTextIndex]
          let currentCharIndex = 0
          this.displayedText = ''
          const typingInterval = setInterval(() => {
            if (currentCharIndex < fullText.length) {
              this.displayedText += fullText[currentCharIndex]
              currentCharIndex++
            } else {
              clearInterval(typingInterval)
            }
          }, 100)
          setTimeout(() => {
            currentTextIndex++
            typeNextText()
          }, fullText.length * 100 + 2000) // wait for typing to finish + 2 seconds
        } else {
          this.step = 2
        }
      }
      typeNextText()
    }
  }
}
</script>
