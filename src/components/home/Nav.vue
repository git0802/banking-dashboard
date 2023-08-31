<script setup>
import { ref, onMounted } from 'vue'
import { useStore } from '../../stores/global.js'

const store = useStore()
</script>

<template>
  <nav
    class="hidden mdb:flex h-screen mdb:h-full w-[30%] max-w-xs min-w-[280px] bg-[#351b5c] select-none"
    :class="{'showMenu': store.navToggle}"
  >
    <div class="flex flex-col w-16 shrink-0 h-full bg-[#402268] py-10">
        <div class="grow">
            <img src="../../assets/img/bank_logo.svg" class="w-8 mx-auto">

            <div class="w-full text-white text-xl mt-12">
                <div class="nav-icons">
                    <i class="ph ph-circles-three-plus"></i>
                </div>
                <div class="nav-icons">
                    <i class="ph ph-chats-circle"></i>
                </div>
                <div class="nav-icons">
                    <i class="ph ph-notepad"></i>
                </div>
                <div class="nav-icons">
                    <i class="ph ph-chart-polar"></i>
                </div>
                <div class="nav-icons">
                    <i class="ph ph-gear"></i>
                </div>
            </div>
        </div>

        <div>
            <div class="nav-icons text-white text-xl">
                <i class="ph ph-caret-double-right"></i>
            </div>
        </div>
    </div>


    <div class="grow px-5 h-full overflow-y-auto overflow-x-none">
      <div class="relative">
        <div @click="store.navToggle = false" class="absolute right-0 mdb:hidden">
          <i class="ph ph-x text-white/80 text-2xl"></i>
        </div>
      </div>

        <div class="mx-auto h-full flex flex-col py-8 text-white">

            <div class="border-b border-stone-100/20">
                <div class="flex justify-between items-center bg-sky-400h mb-1">
                    <div class="text-xs opacity-80">Cash Balance</div>
                    <i class="ph ph-dots-three text-2xl leading-none cursor-pointer"></i>
                </div>
                <div class="text-2xl text-white mb-4">$ 12,800.00</div>
            </div>

            <div class="my-5">
                <div class="text-xs opacity-80 mb-3.5">My Savings</div>

                <div class="flex items-center justify-evenly bg-[#462c6b] py-2 border-b-2  border-[#c371ef] mb-3">
                    <img src="../../assets/img/safe_lock1.svg" class="w-10">
                    <div>
                        <p class="text-base mb-0.5">$ 780.00</p>
                        <p class="text-xs opacity-80">Veipa post</p>
                    </div>
                </div>

                <div class="flex items-center justify-evenly bg-[#0263f2] py-2 border-b-2  border-[#33a9f7]">
                    <img src="../../assets/img/safe_lock2.svg" class="w-10">
                    <div>
                        <p class="text-base mb-0.5">$ 1,100.00</p>
                        <p class="text-xs opacity-80">Emergency</p>
                    </div>
                </div>
            </div>

            <div class="grow flex flex-col justify-end items-center">
                <img src="../../assets/img/upgrade.svg" class="w-[90%]">
                <div class="text-center my-3">
                    <p class="text-xl mb-1">upgrade plan</p>
                    <p class="text-[0.65rem] opacity-80">Upgrade plan for high experience</p>
                </div>
                <button class="w-full text-xs bg-[#c371ef] py-2.5">Upgrade Now</button>
            </div>

        </div>
    </div>
</nav>
</template>
