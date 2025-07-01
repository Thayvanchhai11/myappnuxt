<template>
  <div class="min-h-screen bg-gray-100 text-gray-900 relative">
    <!-- Header -->
    <header class="flex flex-col md:flex-row bg-yellow-500 shadow-lg">
      <!-- Left Logo Section -->
      <div class="bg-black flex items-center justify-center px-6 py-4 md:px-10" style="border-top-right-radius: 2rem;">
        <span class="text-4xl md:text-7xl font-bold text-white tracking-widest">LOGO</span>
      </div>

      <!-- Right Navigation Section -->
      <div class="w-full">
        <!-- Top Yellow Bar -->
        <div class="px-4 py-2 md:px-20">
          <!-- Mobile Menu Button -->
          <div class="flex justify-between items-center md:hidden">
            <div class="text-lg font-bold">Menu</div>
            <button @click="menuOpen = !menuOpen" class="focus:outline-none">
              <svg class="w-6 h-6 text-black" fill="none" stroke="currentColor" viewBox="0 0 24 24">
                <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M4 6h16M4 12h16M4 18h16" />
              </svg>
            </button>
          </div>

          <!-- Navigation Links -->
          <nav
            :class="['flex-col md:flex-row md:flex md:space-x-8 items-start md:items-center mt-4 md:mt-0', menuOpen ? 'flex' : 'hidden']">
            <div class="flex flex-col md:flex-row md:space-x-8 w-full">

              <!-- LỊCH TRỰC TIẾP -->
              <div class="relative group md:py-1" @click="toggleDropdown('lichTrucTiep')">
                <button class="text-black font-medium hover:text-white transition flex items-center space-x-1">
                  <span>LỊCH TRỰC TIẾP</span>
                  <svg class="w-4 h-4 mt-[2px]" fill="none" stroke="currentColor" viewBox="0 0 24 24">
                    <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M19 9l-7 7-7-7" />
                  </svg>
                </button>
                <div
                  class="absolute left-0 z-10 mt-2 w-40 bg-white text-black rounded shadow-md border border-gray-200 hidden group-hover:block"
                  :class="{ 'block': openDropdown === 'lichTrucTiep' && isMobile }">
                  <a href="#" class="block px-4 py-2 hover:bg-gray-100">BÓNG ĐÁ</a>
                  <a href="#" class="block px-4 py-2 hover:bg-gray-100">ĐUA XE</a>
                  <a href="#" class="block px-4 py-2 hover:bg-gray-100">BÓNG RỔ</a>
                  <a href="#" class="block px-4 py-2 hover:bg-gray-100">E-SPORT</a>
                  <a href="#" class="block px-4 py-2 hover:bg-gray-100">CASINO</a>
                </div>
              </div>

              <!-- LỊCH THI ĐẤU -->
              <div class="relative group md:py-1" @click="toggleDropdown('lichThiDau')">
                <button class="text-black font-medium hover:text-white transition flex items-center space-x-1">
                  <span>LỊCH THI ĐẤU</span>
                  <svg class="w-4 h-4 mt-[2px]" fill="none" stroke="currentColor" viewBox="0 0 24 24">
                    <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M19 9l-7 7-7-7" />
                  </svg>
                </button>
                <div
                  class="absolute left-0 z-10 mt-2 w-40 bg-white text-black rounded shadow-md border border-gray-200 hidden group-hover:block"
                  :class="{ 'block': openDropdown === 'lichTrucTiep' && isMobile }">
                  <a href="#" class="block px-4 py-2 hover:bg-gray-100">BÓNG ĐÁ</a>
                  <a href="#" class="block px-4 py-2 hover:bg-gray-100">ĐUA XE</a>
                  <a href="#" class="block px-4 py-2 hover:bg-gray-100">BÓNG RỔ</a>
                  <a href="#" class="block px-4 py-2 hover:bg-gray-100">E-SPORT</a>
                  <a href="#" class="block px-4 py-2 hover:bg-gray-100">CASINO</a>
                </div>
              </div>

              <!-- TỶ LỆ KÈO -->
              <div class="relative group md:py-1" @click="toggleDropdown('tyLeKeo')">
                <button class="text-black font-medium hover:text-white transition flex items-center space-x-1">
                  <span>TỶ LỆ KÈO</span>
                  <svg class="w-4 h-4 mt-[2px]" fill="none" stroke="currentColor" viewBox="0 0 24 24">
                    <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M19 9l-7 7-7-7" />
                  </svg>
                </button>
                <div
                  class="absolute left-0 z-10 mt-2 w-40 bg-white text-black rounded shadow-md border border-gray-200 hidden group-hover:block"
                  :class="{ 'block': openDropdown === 'lichTrucTiep' && isMobile }">
                  <a href="#" class="block px-4 py-2 hover:bg-gray-100">BÓNG ĐÁ</a>
                  <a href="#" class="block px-4 py-2 hover:bg-gray-100">ĐUA XE</a>
                  <a href="#" class="block px-4 py-2 hover:bg-gray-100">BÓNG RỔ</a>
                  <a href="#" class="block px-4 py-2 hover:bg-gray-100">E-SPORT</a>
                  <a href="#" class="block px-4 py-2 hover:bg-gray-100">CASINO</a>
                </div>
              </div>

              <!-- KẾT QUẢ -->
              <div class="relative group md:py-1" @click="toggleDropdown('ketQua')">
                <button class="text-black font-medium hover:text-white transition flex items-center space-x-1">
                  <span>KẾT QUẢ</span>
                  <svg class="w-4 h-4 mt-[2px]" fill="none" stroke="currentColor" viewBox="0 0 24 24">
                    <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M19 9l-7 7-7-7" />
                  </svg>
                </button>
                <div
                  class="absolute left-0 z-10 mt-2 w-40 bg-white text-black rounded shadow-md border border-gray-200 hidden group-hover:block"
                  :class="{ 'block': openDropdown === 'lichTrucTiep' && isMobile }">
                  <a href="#" class="block px-4 py-2 hover:bg-gray-100">BÓNG ĐÁ</a>
                  <a href="#" class="block px-4 py-2 hover:bg-gray-100">ĐUA XE</a>
                  <a href="#" class="block px-4 py-2 hover:bg-gray-100">BÓNG RỔ</a>
                  <a href="#" class="block px-4 py-2 hover:bg-gray-100">E-SPORT</a>
                  <a href="#" class="block px-4 py-2 hover:bg-gray-100">CASINO</a>
                </div>
              </div>

              <!-- PHÒNG CHAT -->
              <div class="relative group md:py-1" @click="toggleDropdown('phongChat')">
                <button class="text-black font-medium hover:text-white transition flex items-center space-x-1">
                  <span>PHÒNG CHAT</span>
                  <svg class="w-4 h-4 mt-[2px]" fill="none" stroke="currentColor" viewBox="0 0 24 24">
                    <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M19 9l-7 7-7-7" />
                  </svg>
                </button>
                <div
                  class="absolute left-0 z-10 mt-2 w-40 bg-white text-black rounded shadow-md border border-gray-200 hidden group-hover:block"
                  :class="{ 'block': openDropdown === 'lichTrucTiep' && isMobile }">
                  <a href="#" class="block px-4 py-2 hover:bg-gray-100">BÓNG ĐÁ</a>
                  <a href="#" class="block px-4 py-2 hover:bg-gray-100">ĐUA XE</a>
                  <a href="#" class="block px-4 py-2 hover:bg-gray-100">BÓNG RỔ</a>
                  <a href="#" class="block px-4 py-2 hover:bg-gray-100">E-SPORT</a>
                  <a href="#" class="block px-4 py-2 hover:bg-gray-100">CASINO</a>
                </div>
              </div>

              <!-- Login Buttons -->
              <div class="flex-col md:flex-row md:space-x-3 mt-3 md:mt-0">
                <button
                  class="bg-white text-black font-bold px-6 py-2 rounded-full shadow hover:bg-gray-200 transition mt-1 md:mt-0">
                  ĐĂNG KÝ
                </button>
                <button
                  class="bg-black text-yellow-200 font-bold px-6 py-2 rounded-full shadow hover:bg-gray-900 border border-yellow-400 transition mt-1 md:mt-0"
                  @click="showUserPanel = !showUserPanel">
                  ĐĂNG NHẬP
                </button>
              </div>
            </div>
          </nav>
        </div>

        <!-- User Info Panel -->
        <transition name="fade">
          <div v-if="showUserPanel" class="fixed top-8 right-8 z-50" @click.self="showUserPanel = false">
            <div
              class="bg-gradient-to-r from-yellow-300 to-yellow-500 rounded-full flex items-center px-4 py-2 shadow-lg border border-yellow-600 relative">
              <div class="flex items-center space-x-2">
                <!-- Coin Dropdown Trigger -->
                <div class="relative">
                  <button
                    class="flex items-center bg-white rounded-full px-2 py-1 border border-yellow-400 focus:outline-none"
                    @click.stop="showCoinDropdown = !showCoinDropdown">
                    <img src="https://cdn-icons-png.flaticon.com/128/616/616490.png" alt="coin" class="w-6 h-6 mr-1" />
                    <span class="font-bold text-black">1000</span>
                    <span
                      class="ml-2 bg-yellow-400 rounded-full w-6 h-6 flex items-center justify-center text-black font-bold text-lg">+</span>
                  </button>
                  <!-- Coin Dropdown -->
                  <transition name="fade">
                    <div v-if="showCoinDropdown"
                      class="absolute left-0 mt-2 w-48 bg-white/80 backdrop-blur-md rounded-2xl shadow-xl border border-gray-200 z-50 p-3"
                      @click.stop>
                      <div class="flex items-center justify-between mb-2">
                        <div class="flex items-center">
                          <img src="https://cdn-icons-png.flaticon.com/128/616/616490.png" alt="coin"
                            class="w-6 h-6 mr-1" />
                          <span class="font-bold text-black text-lg">1000</span>
                        </div>
                        <button @click="showCoinDropdown = false"
                          class="text-black hover:text-red-600 text-xl font-bold">&times;</button>
                      </div>
                      <div class="flex items-center bg-white/60 rounded-xl px-3 py-2 mb-2">
                        <img src="https://cdn-icons-png.flaticon.com/128/616/616494.png" alt="silver"
                          class="w-6 h-6 mr-2" />
                        <span class="text-gray-700 font-semibold">20.000</span>
                      </div>
                      <div class="flex items-center bg-white/60 rounded-xl px-3 py-2 mb-2">
                        <img src="https://cdn-icons-png.flaticon.com/128/616/616495.png" alt="king"
                          class="w-6 h-6 mr-2" />
                        <span class="text-gray-700 font-semibold">20.000</span>
                      </div>
                      <button class="flex items-center w-full justify-start text-yellow-700 font-bold mt-2">
                        <span class="text-xl mr-2">+</span> Nạp thêm
                      </button>
                    </div>
                  </transition>
                </div>
                <!-- Notifications -->
                <button class="relative bg-black rounded-full w-10 h-10 flex items-center justify-center mx-1">
                  <svg class="w-6 h-6 text-yellow-400" fill="none" stroke="currentColor" viewBox="0 0 24 24">
                    <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2"
                      d="M15 17h5l-1.405-1.405A2.032 2.032 0 0118 14.158V11a6.002 6.002 0 00-4-5.659V5a2 2 0 10-4 0v.341C7.67 6.165 6 8.388 6 11v3.159c0 .538-.214 1.055-.595 1.436L4 17h5m6 0v1a3 3 0 11-6 0v-1m6 0H9" />
                  </svg>
                  <span class="absolute -top-1 -right-1 bg-red-600 text-white text-xs rounded-full px-1.5">10</span>
                </button>
                <!-- Mail -->
                <button class="relative bg-black rounded-full w-10 h-10 flex items-center justify-center mx-1">
                  <svg class="w-6 h-6 text-yellow-400" fill="none" stroke="currentColor" viewBox="0 0 24 24">
                    <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2"
                      d="M3 8l7.89 5.26a2 2 0 002.22 0L21 8M5 19h14a2 2 0 002-2V7a2 2 0 00-2-2H5a2 2 0 00-2 2v10a2 2 0 002 2z" />
                  </svg>
                  <span class="absolute -top-1 -right-1 bg-red-600 text-white text-xs rounded-full px-1.5">2</span>
                </button>
                <!-- Calendar -->
                <button class="bg-black rounded-full w-10 h-10 flex items-center justify-center mx-1">
                  <svg class="w-6 h-6 text-yellow-400" fill="none" stroke="currentColor" viewBox="0 0 24 24">
                    <rect x="3" y="4" width="18" height="18" rx="2" stroke-width="2" stroke="currentColor"
                      fill="none" />
                    <path d="M16 2v4M8 2v4M3 10h18" stroke-width="2" stroke="currentColor" />
                  </svg>
                </button>
                <!-- User Avatar -->
                <div class="relative flex items-center ml-2">
                  <img src="https://randomuser.me/api/portraits/men/32.jpg" alt="avatar"
                    class="w-12 h-12 rounded-full border-4 border-yellow-400" />
                  <span
                    class="absolute -bottom-1 -right-1 bg-yellow-400 text-black text-xs font-bold rounded-full px-2 py-0.5 border border-white">20</span>
                </div>
              </div>
              <!-- User Greeting -->
              <div class="absolute -top-6 left-1/2 -translate-x-1/2 text-xs text-black font-semibold">
                Xin chào, <span class="text-red-600">NguyenVanDen</span>
              </div>
              <!-- Close Button -->
              <button @click="showUserPanel = false"
                class="absolute top-1 right-1 text-black hover:text-red-600 text-xl font-bold">&times;</button>
            </div>
          </div>
        </transition>

        <!-- Bottom Black Bar -->
        <div class="w-full bg-black py-3 px-4 md:px-20">
          <div class="flex flex-col md:flex-row md:items-center md:space-x-8 text-yellow-200">
            <div class="flex flex-wrap gap-x-4 gap-y-2 text-sm">
              <a href="#" class="font-medium hover:text-white transition">📢 Bảng Tin</a>
              <a href="#" class="font-medium hover:text-white transition">🎬 Reels</a>
              <a href="#" class="font-medium hover:text-white transition">📺 Highlight</a>
              <a href="#" class="font-medium hover:text-white transition">👑 Tip Kèo</a>
              <a href="#" class="font-medium hover:text-white transition">🎥 Phim Ảnh</a>
              <a href="#" class="font-medium hover:text-white transition">📖 Truyện Tranh</a>
            </div>

            <!-- Language Switch -->
            <div class="flex space-x-2 mt-3 md:mt-0 md:ml-10">
              <button
                class="flex items-center bg-white text-black font-bold px-3 py-1 rounded-full shadow hover:bg-gray-200 transition border border-gray-200">
                <span class="flex items-center">
                  <span class="w-5 h-5 rounded-full bg-red-500 flex items-center justify-center mr-2">
                    <span class="text-white text-xs">★</span>
                  </span>
                  TIẾNG VIỆT
                </span>
              </button>
              <button
                class="flex items-center bg-white w-20 text-black font-bold rounded-full shadow hover:bg-gray-200 transition border border-gray-200">
                <span class="ml-2 w-5 h-5 rounded-full bg-blue-600 flex items-center justify-center mr-2"></span>
                EN
              </button>
            </div>
          </div>
        </div>
      </div>
    </header>

    <main class="p-4 md:p-8 bg-[#ededed]">
      <!-- Top Carousel Section -->
      <section class="mb-8">
        <div class="flex items-center justify-between mb-2">
          <div></div>
          <div class="flex items-center space-x-2">
            <span class="text-gray-500 text-sm font-semibold cursor-pointer hover:underline">Xem tất cả</span>
            <button class="bg-white rounded-full shadow px-2 py-2 flex items-center justify-center">
              <svg class="w-6 h-6 text-gray-400" fill="none" stroke="currentColor" viewBox="0 0 24 24">
                <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M15 19l-7-7 7-7" />
              </svg>
            </button>
            <button class="bg-white rounded-full shadow px-2 py-2 flex items-center justify-center">
              <svg class="w-6 h-6 text-gray-400" fill="none" stroke="currentColor" viewBox="0 0 24 24">
                <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M9 5l7 7-7 7" />
              </svg>
            </button>
          </div>
        </div>
        <div class="flex space-x-4 overflow-x-auto pb-2 scrollbar-thin scrollbar-thumb-gray-300">
          <div v-for="i in 7" :key="'top-'+i" class="min-w-[260px] max-w-[260px] bg-white rounded-2xl shadow border-2 border-yellow-200 relative overflow-hidden">
            <img src="https://images.unsplash.com/photo-1517649763962-0c623066013b?auto=format&fit=crop&w=400&q=80"
              class="w-full h-32 object-cover" />
            <div class="absolute top-2 right-2 bg-red-500 text-white text-xs px-2 py-0.5 rounded">HOT</div>
            <div class="absolute bottom-2 right-2 bg-yellow-400 text-black text-xs px-2 py-0.5 rounded">LIVE</div>
            <div class="p-2">
              <div class="font-bold text-sm flex items-center">
                <span v-if="i % 3 === 1" class="mr-1 text-xl">🏀</span>
                <span v-else-if="i % 3 === 2" class="mr-1 text-xl">🎮</span>
                <span v-else class="mr-1 text-xl">⚽</span>
                Team A vs Team B
              </div>
              <div class="text-xs text-gray-700">BLV NONAME</div>
            </div>
            <div class="absolute bottom-2 left-2">
              <button v-if="i % 2 === 0" class="bg-yellow-400 text-black text-xs px-2 py-0.5 rounded flex items-center">
                <svg class="w-4 h-4 mr-1" fill="none" stroke="currentColor" viewBox="0 0 24 24">
                  <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M5 13l4 4L19 7" />
                </svg>
                Đặt lịch
              </button>
              <button v-else class="bg-yellow-400 text-black text-xs px-2 py-0.5 rounded flex items-center">
                <svg class="w-4 h-4 mr-1" fill="none" stroke="currentColor" viewBox="0 0 24 24">
                  <circle cx="12" cy="12" r="10" stroke="currentColor" stroke-width="2" fill="none"/>
                  <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M8 12h8" />
                </svg>
                Hủy lịch
              </button>
            </div>
          </div>
        </div>
      </section>

      <!-- SECTION_Thumbnails -->
      <section class="bg-white rounded-2xl shadow border border-purple-400 p-4 mb-8">
        <div class="flex items-center justify-between mb-2">
          <span class="text-xs text-gray-400 font-semibold">SECTION_Thumbnails</span>
          <button
            class="text-gray-600 text-xs font-bold flex items-center space-x-1 hover:underline"
            @click="showThumbnails = !showThumbnails"
          >
            <span>{{ showThumbnails ? 'Thu gọn' : 'Xem thêm' }}</span>
            <svg class="w-4 h-4" fill="none" stroke="currentColor" viewBox="0 0 24 24">
              <path
                stroke-linecap="round"
                stroke-linejoin="round"
                stroke-width="2"
                :d="showThumbnails ? 'M19 9l-7 7-7-7' : 'M19 15l-7-7-7 7'"
              />
            </svg>
          </button>
        </div>
        <div v-if="showThumbnails" class="grid grid-cols-1 sm:grid-cols-2 md:grid-cols-3 lg:grid-cols-4 gap-4">
          <div v-for="i in 8" :key="'thumb-'+i" class="bg-[#f8f6f2] rounded-2xl border-2 border-yellow-200 relative overflow-hidden">
            <img src="https://images.unsplash.com/photo-1517649763962-0c623066013b?auto=format&fit=crop&w=400&q=80"
              class="w-full h-32 object-cover" />
            <div class="absolute top-2 right-2 bg-red-500 text-white text-xs px-2 py-0.5 rounded">HOT</div>
            <div v-if="i % 3 === 1" class="absolute bottom-2 right-2 bg-yellow-400 text-black text-xs px-2 py-0.5 rounded">LIVE</div>
            <div class="p-2">
              <div class="font-bold text-sm flex items-center">
                <span v-if="i % 3 === 1" class="mr-1 text-xl">🏀</span>
                <span v-else-if="i % 3 === 2" class="mr-1 text-xl">🎮</span>
                <span v-else class="mr-1 text-xl">⚽</span>
                Team A vs Team B
              </div>
              <div class="text-xs text-gray-700">BLV NONAME</div>
            </div>
            <div class="absolute bottom-2 left-2">
              <button v-if="i % 2 === 0" class="bg-yellow-400 text-black text-xs px-2 py-0.5 rounded flex items-center">
                <svg class="w-4 h-4 mr-1" fill="none" stroke="currentColor" viewBox="0 0 24 24">
                  <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M5 13l4 4L19 7" />
                </svg>
                Đặt lịch
              </button>
              <button v-else class="bg-yellow-400 text-black text-xs px-2 py-0.5 rounded flex items-center">
                <svg class="w-4 h-4 mr-1" fill="none" stroke="currentColor" viewBox="0 0 24 24">
                  <circle cx="12" cy="12" r="10" stroke="currentColor" stroke-width="2" fill="none"/>
                  <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M8 12h8" />
                </svg>
                Hủy lịch
              </button>
            </div>
          </div>
        </div>
      </section>
    </main>
  </div>
</template>

<script setup>
import { ref, onMounted } from 'vue'

const menuOpen = ref(false)
const openDropdown = ref(null)
const isMobile = ref(false)
const showUserPanel = ref(false)
const showCoinDropdown = ref(false)
const showThumbnails = ref(true) // for expand/collapse

function toggleDropdown(name) {
  if (isMobile.value) {
    openDropdown.value = openDropdown.value === name ? null : name
  }
}

onMounted(() => {
  const update = () => {
    isMobile.value = window.innerWidth < 768
    if (!isMobile.value) openDropdown.value = null
  }
  update()
  window.addEventListener('resize', update)
})
</script>

<style>
.fade-enter-active,
.fade-leave-active {
  transition: opacity 0.2s;
}

.fade-enter-from,
.fade-leave-to {
  opacity: 0;
}
</style>