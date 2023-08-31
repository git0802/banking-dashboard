<script setup>
import { useStore } from '../../stores/global.js'

const store = useStore()

import Head from '@/components/home/body/Head.vue'
import RightContent from '@/components/home/body/RightContent.vue'
import LeftContent from '@/components/home/body/LeftContent.vue'
</script>

<template>
  <div class="grow h-full overflow-y-auto select-none" :style="{pointerEvents: store.navToggle ? 'none' : 'all'}">
    <div class="max-w-5xl mx-auto h-fit px-3 xsm:px-4 sm:px-8 pb-3">

        <Head />
        
        <div class="w-full lgb:flex h-full">
            <RightContent />
            <LeftContent />
        </div>

    </div>
    
</div>
</template>