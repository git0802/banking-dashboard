<script setup>
import SpendingChart from '@/components/home/body/SpendingChart.vue'
</script>

<template>
  <div class="w-full lgb:w-[60%] grow h-full mr-5">
      <div class="bg-white h-[300px]h rounded-md shadow mb-4 p-3 sm:p-5">
          <div class="flex justify-between text-[#351b5c] mb-3">
              <p class="text-base font-semibold">Spend Summary</p>
              <div class="flex items-center cursor-pointer">
                  <i class="ph ph-calendar mr-1.5"></i>
                  <span class="text-xs mr-1.5">Month</span>
                  <i class="ph ph-caret-down text-[#33a9f7]"></i>
              </div>
          </div>
          
          <SpendingChart />
      </div>

      <div class="sm:grid grid-cols-2 gap-5">
          <div class="w-full xsm:w-[70%] sm:w-full mx-auto">
              <div class="relative w-full rounded-md overflow-hidden mb-3">
                  <img src="../../../assets/img/card_bg1.svg" class="w-full">
                  <div class="absolute top-0 w-full h-full flex flex-col justify-between text-white text-sm px-5 py-4 opacity-90">
                      <div class="flex justify-between">
                          <p class="font-semibold">Maze Bank</p>
                          <p>$ 200.00</p>
                      </div>

                      <div class="flex items-end justify-between">
                          <p>**** 5430</p>
                          <img src="../../../assets/img/mastercard_logo.svg" class="w-11">
                      </div>
                  </div>
              </div>

              <div class="relative w-full rounded-md overflow-hidden">
                  <img src="../../../assets/img/card_bg2.svg" class="w-full">
                  <div class="absolute top-0 w-full h-full flex flex-col justify-between text-white text-sm px-5 py-4 opacity-90">
                      <div class="flex justify-between">
                          <p class="font-semibold">Maze Bank</p>
                          <p>$ 800.00</p>
                      </div>

                      <div class="flex items-end justify-between">
                          <p>**** 1054</p>
                          <img src="../../../assets/img/mastercard_logo.svg" class="w-11">
                      </div>
                  </div>
              </div>
          </div>

          <div class="h-fit bg-white rounded-md shadow p-5 mt-4 sm:mt-0">
              <p class="text-base font-semibold text-[#351b5c] mb-4">Quick transfer</p>

              <div class="flex justify-between items-center">
                  <div class="flex cursor-pointer">
                      <img src="../../../assets/img/avatars/avt1.jpg" class="w-9 rounded-full mr-2.5 border-2 border-white">
                      <img src="../../../assets/img/avatars/avt2.jpg" class="w-9 -ml-5 rounded-full mr-2.5 border-2 border-white">
                      <img src="../../../assets/img/avatars/avt4.jpg" class="w-9 -ml-5 rounded-full mr-2.5 border-2 border-white">
                      <div class="w-9 h-9 flex justify-center items-center bg-[#351b5c] -ml-5 rounded-full text-white border-2 border-white">
                          <i class="ph ph-plus"></i>
                      </div>
                  </div>

                  <div class="text-[#33a9f7] text-xs font-semibold cursor-pointer">
                      All <i class="ph ph-caret-right ml-0.5"></i>
                  </div>
              </div>

              <p class="text-xs text-gray-500 my-5">Provide amount</p>

              <form>
                  <input type="text" class="w-full text-3xl text-[#351b5c] bg-none border-none mb-5" value="$ 20.00">
                  <button class="text-xs text-white bg-[#0263f2] px-6 py-2.5" disabled>Send money</button>
              </form>
          </div>
      </div>
  </div>
</template>