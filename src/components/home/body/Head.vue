<script setup>
import { ref, onMounted } from 'vue'
import { useStore } from '../../../stores/global.js'

const store = useStore()

const today = ref('-- ---- ----')

onMounted(() => {
  // create date display at top bar
  const currentDate = new Date()
  
  //format the date
  var formattedDate = currentDate.toLocaleDateString('en-US', {
      day: 'numeric',
      month: 'long',
      year: 'numeric'
  })
  
  // set the value to element
  today.value = "Today, " + formattedDate
})
</script>

<template>
  <div class="py-5">
    <div class="flex justify-between items-center mb-2">
        <div class="flex items-center">
            <i class="ph ph-list mdb:hidden text-3xl text-[#351b5c] cursor-pointer md:mr-5" @click="store.navToggle = true"></i>
            <h1 class="hidden md:block text-2xl lg:text-3xl text-[#351b5c]">Hi, Zahara</h1>
        </div>

        <div class="flex items-center grow w-24 mic:max-w-[200px] xl:max-w-[250px] bg-white rounded-md px-2.5 py-1 mx-2 shadow overflow-hidden">
            <i class="ph ph-magnifying-glass text-[#c371ef] mr-2 text-lg"></i>
            <input type="text" class="border-none bg-transparent text-gray-500 text-sm placeholder:text-transparent xsm:placeholder:text-gray-500" placeholder="Search Here...">
        </div>

        <div class="flex items-center">
            <div class="relative mr-3 xsm:mr-6 mdb:mr-10 cursor-pointer">
                <i class="ph ph-bell text-2xl text-gray-500"></i>
                <div class="absolute top-0 -right-0.5 rounded-full bg-red-500 text-white text-xs w-4 text-center">3</div>
            </div>

            <div class="flex items-center cursor-pointer shrink-0">
                <img src="../../../assets/img/avatars/avt3.jpg" class="w-8 rounded-full sm:mr-2.5">
                <div class="hidden sm:block text-xs mr-2.5">
                    <p class="text-[#351b5c] font-semibold">Zahara</p>
                    <p class="text-gray-500">Customer</p>
                </div>
                <i class="ph ph-caret-down hidden sm:block text-[#33a9f7]"></i>
            </div>
        </div>
    </div>

    <p class="text-gray-500 text-xs">{{today}}</p>
</div>
</template>