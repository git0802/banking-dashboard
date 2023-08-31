<script setup>
import { ref } from 'vue'
import { Chart as ChartJS, ArcElement, Tooltip, Legend } from 'chart.js'
import { Doughnut } from 'vue-chartjs'

ChartJS.register(ArcElement, Tooltip, Legend)

const doughData = ref({
  labels: ['Emergency', 'Spending'],
  datasets: [{
      label: 'Expenditure',
      data: [70, 30],
      backgroundColor: ['#33a9f7','#0263f2'],
      hoverOffset: 4,
      borderColor: ['#33a9f7','#0263f2'],
      borderJoinStyle: 'miter',
      hoverBorderWidth: 8,
      cutout: '73%',
      spacing: 1,
      offset: 10
  }]
})

const doughOptions = ref({
  options: {
    responsive: true,
    plugins: {
      legend: {
        display: false,
      },
      tooltip: {
        backgroundColor: 'rgba(53, 27, 92, 0.8)',
        caretPadding: 5,
        boxWidth: 5,
        usePointStyle: 'triangle',
        boxPadding: 3
      }
    }
  }
})
</script>

<template>
  <div class="w-[70%] xsm:w-[50%] mx-auto">
    <Doughnut :data="doughData" :options="doughOptions" />
  </div>
</template>