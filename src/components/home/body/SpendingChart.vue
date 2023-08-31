<script setup>
import { ref, onMounted } from 'vue'
import { Line } from "vue-chartjs"
import {
 Chart as ChartJS,
  Title,
  Tooltip,
  Legend,
  LineElement,
  LinearScale,
  CategoryScale,
  PointElement,
  Filler
 } from "chart.js"

 ChartJS.register(
  Title,
  Tooltip,
  Legend,
  LineElement,
  LinearScale,
  CategoryScale,
  PointElement,
  Filler
 )

// line chart options
let options = {
  borderWidth: 2,
  cubicInterpolationMode: 'monotone', // make the line curvy over zigzag
  pointRadius: 2,
  pointHoverRadius: 5,
  pointHoverBackgroundColor: '#fff',
  pointHoverBorderWidth: 4
}

let tooltipOptions = {
  backgroundColor: 'rgba(53, 27, 92, 0.8)',
  caretPadding: 5,
  boxWidth: 5,
  usePointStyle: 'triangle',
  boxPadding: 3
}

//create gradients for fill bg
let createGradient = (ctx, color) => {
  const canvas = ctx.chart.ctx
  const gradient = canvas.createLinearGradient(0,0,0,290)
  gradient.addColorStop(0, color)
  gradient.addColorStop(1, 'rgba(0, 0, 0, 0)')
  return gradient
}

const lineData = ref({
  labels: ['May', 'Jun', 'Jul', 'Aug', 'Sep', 'Oct', 'Nov', 'Dec'],
  datasets: [
    {
      label: 'Spending',
      data: [310,300,370,295,350,300,230,290],
      ...options,
      borderColor: '#c371ef',
      fill: 'start',
      backgroundColor: (ctx) => createGradient(ctx, 'rgba(195, 113, 239, 0.15)')
    },
    {
      label: 'Emergency',
      data: [150,230,195,260,220,300,320,490],
      ...options,
      borderColor: '#33a9f7',
      fill: 'start',
      backgroundColor: (ctx) => createGradient(ctx, 'rgba(51, 169, 247, 0.3)')
    }
  ]
})
  
const lineOptions = ref({
    responsive: true,
    plugins: {
      legend: {
        display: false, // hide display data about the dataset
      },
      tooltip: {
        backgroundColor: 'rgba(53, 27, 92, 0.8)',
        caretPadding: 5,
        boxWidth: 5,
        usePointStyle: 'triangle',
        boxPadding: 3
      },
      scales: {
      x: {
        grid: {
          display: false // set display to false to hide the x-axis grid
        },
        beginAtZero: true
      },
      y: {
        ticks: {
          callback: function(value, index, values) {
            return '$ ' + value // prefix '$' to the dataset values
          },
          stepSize: 100
        }
      }
    }
  }
})
</script>

<template>
  <Line :data="lineData" :options="lineOptions" class="w-full" />
</template>