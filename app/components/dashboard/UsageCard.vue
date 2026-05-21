<template>
  <div class="bg-white border border-gray-200 rounded-lg p-6 hover:shadow-lg transition">
    <!-- Header -->
    <div class="flex items-center gap-3 mb-6">
      <span class="text-3xl">{{ icon }}</span>
      <h3 class="text-base font-bold text-gray-900">{{ title }}</h3>
    </div>

    <!-- Metrics -->
    <div class="mb-6 space-y-4">
      <div>
        <p class="text-gray-500 font-semibold uppercase text-xs tracking-wide mb-1">
          {{ title === 'Voice' ? 'Minutes' : title === 'Video' ? 'Minutes' : 'Messages' }}
        </p>
        <p class="text-3xl font-bold text-gray-900">{{ value }}</p>
      </div>
      <div>
        <p class="text-gray-500 font-semibold uppercase text-xs tracking-wide mb-1">Cost</p>
        <p class="text-2xl font-bold text-gray-900">{{ cost }}</p>
      </div>
    </div>

    <!-- Chart Container -->
    <div class="mb-6">
      <canvas :id="`chart-${title}`" ref="chartRef" height="120"></canvas>
    </div>

    <!-- Legend -->
    <div class="flex items-center justify-start gap-6 text-xs flex-wrap">
      <div v-for="(label, idx) in legendLabels" :key="idx" class="flex items-center gap-2">
        <div 
          :class="[
            'w-2 h-2 rounded-full',
            idx === 0 ? 'bg-teal-500' : idx === 1 ? 'bg-yellow-500' : 'bg-gray-900'
          ]"
        ></div>
        <span class="text-gray-600">{{ label }}</span>
      </div>
    </div>
  </div>
</template>

<script setup>
import { ref, onMounted } from 'vue'
import Chart from 'chart.js/auto'

const props = defineProps({
  title: {
    type: String,
    required: true
  },
  icon: {
    type: String,
    required: true
  },
  value: {
    type: String,
    default: '0'
  },
  cost: {
    type: String,
    default: '$0.00'
  }
})

const chartRef = ref(null)
let chartInstance = null

const legendLabels = ref([])
const chartData = ref({})

// Set up legend labels and chart data based on title
const setupChartData = () => {
  if (props.title === 'Voice') {
    legendLabels.value = ['Inbound', 'Outbound', 'Cost']
    chartData.value = {
      labels: ['May 14', 'May 15', 'May 16', 'May 17', 'May 18', 'May 19', 'May 20'],
      datasets: [
        {
          label: 'Inbound',
          data: [0, 0, 0, 0, 0, 0, 0],
          borderColor: '#14b8a6',
          backgroundColor: 'rgba(20, 184, 166, 0.1)',
          tension: 0.4,
          fill: true,
          borderWidth: 2,
          pointRadius: 4,
          pointBackgroundColor: '#14b8a6',
          pointBorderColor: '#fff',
          pointBorderWidth: 2,
        },
        {
          label: 'Outbound',
          data: [0, 0, 0, 0, 0, 0, 0],
          borderColor: '#eab308',
          backgroundColor: 'rgba(234, 179, 8, 0.1)',
          tension: 0.4,
          fill: true,
          borderWidth: 2,
          pointRadius: 4,
          pointBackgroundColor: '#eab308',
          pointBorderColor: '#fff',
          pointBorderWidth: 2,
        },
        {
          label: 'Cost',
          data: [0, 0, 0, 0, 0, 0, 0],
          borderColor: '#111827',
          backgroundColor: 'transparent',
          tension: 0.4,
          fill: false,
          borderWidth: 2,
          borderDash: [5, 5],
          pointRadius: 4,
          pointBackgroundColor: '#111827',
          pointBorderColor: '#fff',
          pointBorderWidth: 2,
        }
      ]
    }
  } else if (props.title === 'Video') {
    legendLabels.value = ['720p', '1080p', 'Cost']
    chartData.value = {
      labels: ['May 14', 'May 15', 'May 16', 'May 17', 'May 18', 'May 19', 'May 20'],
      datasets: [
        {
          label: '720p',
          data: [0, 0, 0, 0, 0, 0, 0],
          borderColor: '#14b8a6',
          backgroundColor: 'rgba(20, 184, 166, 0.1)',
          tension: 0.4,
          fill: true,
          borderWidth: 2,
          pointRadius: 4,
          pointBackgroundColor: '#14b8a6',
          pointBorderColor: '#fff',
          pointBorderWidth: 2,
        },
        {
          label: '1080p',
          data: [0, 0, 0, 0, 0, 0, 0],
          borderColor: '#eab308',
          backgroundColor: 'rgba(234, 179, 8, 0.1)',
          tension: 0.4,
          fill: true,
          borderWidth: 2,
          pointRadius: 4,
          pointBackgroundColor: '#eab308',
          pointBorderColor: '#fff',
          pointBorderWidth: 2,
        },
        {
          label: 'Cost',
          data: [0, 0, 0, 0, 0, 0, 0],
          borderColor: '#111827',
          backgroundColor: 'transparent',
          tension: 0.4,
          fill: false,
          borderWidth: 2,
          borderDash: [5, 5],
          pointRadius: 4,
          pointBackgroundColor: '#111827',
          pointBorderColor: '#fff',
          pointBorderWidth: 2,
        }
      ]
    }
  } else if (props.title === 'Messaging') {
    legendLabels.value = ['SMS', 'MMS', 'Cost']
    chartData.value = {
      labels: ['May 14', 'May 15', 'May 16', 'May 17', 'May 18', 'May 19', 'May 20'],
      datasets: [
        {
          label: 'SMS',
          data: [0, 0, 0, 0, 0, 0, 0],
          borderColor: '#14b8a6',
          backgroundColor: 'rgba(20, 184, 166, 0.1)',
          tension: 0.4,
          fill: true,
          borderWidth: 2,
          pointRadius: 4,
          pointBackgroundColor: '#14b8a6',
          pointBorderColor: '#fff',
          pointBorderWidth: 2,
        },
        {
          label: 'MMS',
          data: [0, 0, 0, 0, 0, 0, 0],
          borderColor: '#eab308',
          backgroundColor: 'rgba(234, 179, 8, 0.1)',
          tension: 0.4,
          fill: true,
          borderWidth: 2,
          pointRadius: 4,
          pointBackgroundColor: '#eab308',
          pointBorderColor: '#fff',
          pointBorderWidth: 2,
        },
        {
          label: 'Cost',
          data: [0, 0, 0, 0, 0, 0, 0],
          borderColor: '#111827',
          backgroundColor: 'transparent',
          tension: 0.4,
          fill: false,
          borderWidth: 2,
          borderDash: [5, 5],
          pointRadius: 4,
          pointBackgroundColor: '#111827',
          pointBorderColor: '#fff',
          pointBorderWidth: 2,
        }
      ]
    }
  }
}

const createChart = () => {
  if (!chartRef.value) return

  const ctx = chartRef.value.getContext('2d')

  if (chartInstance) {
    chartInstance.destroy()
  }

  chartInstance = new Chart(ctx, {
    type: 'line',
    data: chartData.value,
    options: {
      responsive: true,
      maintainAspectRatio: false,
      interaction: {
        mode: 'index',
        intersect: false,
      },
      plugins: {
        legend: {
          display: false,
        },
        tooltip: {
          backgroundColor: 'rgba(0, 0, 0, 0.8)',
          padding: 12,
          titleColor: '#fff',
          bodyColor: '#fff',
          borderColor: 'rgba(255, 255, 255, 0.2)',
          borderWidth: 1,
          cornerRadius: 4,
          titleFont: {
            size: 12,
            weight: 'bold'
          },
          bodyFont: {
            size: 11
          }
        }
      },
      scales: {
        x: {
          grid: {
            display: true,
            drawBorder: false,
            color: 'rgba(0, 0, 0, 0.05)',
          },
          ticks: {
            color: '#9ca3af',
            font: {
              size: 11
            }
          }
        },
        y: {
          beginAtZero: true,
          grid: {
            display: true,
            drawBorder: false,
            color: 'rgba(0, 0, 0, 0.05)',
          },
          ticks: {
            color: '#9ca3af',
            font: {
              size: 11
            },
            callback: function(value) {
              return value
            }
          }
        }
      }
    }
  })
}

onMounted(() => {
  setupChartData()
  createChart()
})
</script>

<style scoped>
.transition {
  transition-duration: 200ms;
}
</style>