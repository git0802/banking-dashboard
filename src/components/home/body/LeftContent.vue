<script setup>
import TransactionChart from '@/components/home/body/TransactionChart.vue'
</script>

<template>
  <div class="flex flex-col sm:flex-row lgb:flex-col items-stretch bg-white w-full lgb:w-[35%] h-fit p-0 sm:p-5 lgb:p-0 my-5 lgb:my-0 rounded-md shadow text-[#351b5c] overflow-hidden">
    <div class="flex-1 p-4 sm:p-0 lgb:p-5">
        <p class="text-base font-semibold text-center mb-4">Financial Record</p>
        
        <TransactionChart />

        <div class="flex items-center text-xs mt-4">
            <div class="flex-1 text-center border-r">
                <div class="w-2 h-2 rounded-full bg-[#0263f2] inline-block mr-1"></div>
                Emergency 70%
            </div>
            <div class="flex-1 text-center">
                <div class="w-2 h-2 rounded-full bg-[#33a9f7] inline-block mr-1"></div>
                Spending 30%
            </div>
        </div>

        <div class="text-center my-6 sm:my-0 sm:mt-6 lgb:my-6">
            <button class="text-xs text-white bg-[#0263f2] px-6 py-2.5">View all record</button>
        </div>
    </div>

    <div class="flex-1 flex flex-col sm:border lgb:border-none rounded lgb:rounded-none">
        <div class="grow p-4 sm:p-0">
            <div class="text-center mb-7">
                <img src="../../../assets/img/operator.svg" class="w-[50%] inline-block mb-4">
                <p class="text-[#351b5c] text-lg font-semibold">We're here to help you</p>
            </div>
        </div>

        <div class="flex justify-between px-5 py-3 bg-[#cde7fe]">
            <div class="text-xs">
                <p class="font-semibold">Tola Speed</p>
                <p>Customer Service</p>
            </div>
            <div class="relative w-10">
                <div class="absolute -top-8 flex justify-center items-center rounded-full text-white bg-[#351b5c] w-10 h-10 cursor-pointer">
                    <i class="ph ph-chats-circle text-xl"></i>
                </div>
            </div>
        </div>
    </div>
</div>
</template>