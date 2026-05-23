<template>
  <DashboardLayout>
    <div class="p-24 w-full">
      <!-- Page Title -->
      <h1 class="text-4xl font-light text-gray-900 mb-16">Programmable Video Communication</h1>

      <!-- Usage Section -->
      <div class="mb-12">
        <h2 class="text-sm font-bold text-gray-900 uppercase tracking-wide mb-8">USAGE</h2>

        <div class="grid grid-cols-1 lg:grid-cols-3 gap-8">
          <!-- Left: Chart -->
          <div class="lg:col-span-2 bg-white border border-gray-200 rounded-lg p-6">
            <!-- Metrics Row -->
            <div class="grid grid-cols-2 gap-8 mb-6 pb-6 border-b border-gray-200">
              <div>
                <p class="text-gray-500 font-semibold uppercase text-xs tracking-wide mb-2">Minutes</p>
                <p class="text-3xl font-bold text-gray-900">0</p>
              </div>
              <div>
                <p class="text-gray-500 font-semibold uppercase text-xs tracking-wide mb-2">Cost</p>
                <p class="text-2xl font-bold text-gray-900">$0.00</p>
              </div>
            </div>

            <!-- Chart -->
            <div class="h-64 mb-6">
              <canvas ref="usageChartRef" height="160"></canvas>
            </div>

            <!-- Legend -->
            <div class="flex items-center justify-center gap-8 text-sm">
              <div class="flex items-center gap-2">
                <div class="w-2 h-2 rounded-full bg-teal-500"></div>
                <span class="text-gray-600">Minutes</span>
              </div>
              <div class="flex items-center gap-2">
                <div class="w-2 h-2 rounded-full bg-yellow-500"></div>
                <span class="text-gray-600">Cost</span>
              </div>
            </div>
          </div>

          <!-- Right: Pie Chart -->
          <div class="bg-white border border-gray-200 rounded-lg p-6 flex flex-col items-center justify-center">
            <h3 class="text-sm font-bold text-gray-900 uppercase tracking-wide mb-8">Video Quality Breakdown</h3>
            <div class="h-48 w-48">
              <canvas ref="qualityChartRef" height="200"></canvas>
            </div>
            <div class="flex items-center justify-center gap-6 text-xs mt-6">
              <div class="flex items-center gap-2">
                <div class="w-2 h-2 rounded-full bg-blue-600"></div>
                <span class="text-gray-600">1080p</span>
              </div>
              <div class="flex items-center gap-2">
                <div class="w-2 h-2 rounded-full bg-pink-500"></div>
                <span class="text-gray-600">720p</span>
              </div>
            </div>
          </div>
        </div>
      </div>

      <!-- Feature Cards -->
      <div class="grid grid-cols-1 md:grid-cols-2 gap-8">
        <!-- Card 1 -->
        <div class="bg-white border border-gray-200 rounded-lg p-6 hover:shadow-lg transition">
          <div class="flex items-start gap-3 mb-4">
            <div class="relative">
              <span class="absolute -top-2 -right-2 inline-flex items-center justify-center px-2 py-1 text-xs font-bold leading-none text-white transform translate-x-1/2 -translate-y-1/2 bg-red-600 rounded-full">
                NEW
              </span>
              <span class="text-3xl">⭐</span>
            </div>
            <div>
              <h3 class="font-bold text-gray-900">Copy. Paste. Done. with Video Conferences</h3>
            </div>
          </div>
          <p class="text-gray-600 text-sm">
            Video Conference Rooms allow you to easily setup and customize video meeting rooms and embed them with a single snippet any website or application.
          </p>
        </div>

        <!-- Card 2 -->
        <div class="bg-white border border-gray-200 rounded-lg p-6 hover:shadow-lg transition">
          <div class="flex items-start gap-3 mb-4">
            <span class="text-3xl">&lt;/&gt;</span>
            <div>
              <h3 class="font-bold text-gray-900">Build Anything, with Advanced Rooms</h3>
            </div>
          </div>
          <p class="text-gray-600 text-sm">
            Advanced Video Rooms allow you to take complete control of your video experience providing feature rich building blocks you can use to customize your application.
          </p>
        </div>
      </div>
    </div>

   
  </DashboardLayout>
</template>

<script setup>
import { ref, onMounted } from 'vue'
import Chart from 'chart.js/auto'

const usageChartRef = ref(null)
const qualityChartRef = ref(null)
let usageChart = null
let qualityChart = null

const createUsageChart = () => {
  if (!usageChartRef.value) return

  const ctx = usageChartRef.value.getContext('2d')

  if (usageChart) {
    usageChart.destroy()
  }

  usageChart = new Chart(ctx, {
    type: 'line',
    data: {
      labels: ['May 14', 'May 15', 'May 16', 'May 17', 'May 18', 'May 19', 'May 20', 'May 21'],
      datasets: [
        {
          label: 'Minutes',
          data: [0, 0, 0, 0, 0, 0, 0, 0],
          borderColor: '#14b8a6',
          backgroundColor: 'rgba(20, 184, 166, 0.05)',
          tension: 0.4,
          fill: true,
          borderWidth: 2,
          pointRadius: 5,
          pointBackgroundColor: '#14b8a6',
          pointBorderColor: '#fff',
          pointBorderWidth: 2,
        },
        {
          label: 'Cost',
          data: [0, 0, 0, 0, 0, 0, 0, 0],
          borderColor: '#eab308',
          backgroundColor: 'transparent',
          tension: 0.4,
          fill: false,
          borderWidth: 2,
          pointRadius: 5,
          pointBackgroundColor: '#eab308',
          pointBorderColor: '#fff',
          pointBorderWidth: 2,
        }
      ]
    },
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
            }
          }
        }
      }
    }
  })
}

const createQualityChart = () => {
  if (!qualityChartRef.value) return

  const ctx = qualityChartRef.value.getContext('2d')

  if (qualityChart) {
    qualityChart.destroy()
  }

  qualityChart = new Chart(ctx, {
    type: 'doughnut',
    data: {
      labels: ['1080p', '720p'],
      datasets: [
        {
          data: [0, 0],
          backgroundColor: [
            '#2563eb',
            '#ec4899'
          ],
          borderColor: '#fff',
          borderWidth: 3,
        }
      ]
    },
    options: {
      responsive: true,
      maintainAspectRatio: false,
      plugins: {
        legend: {
          display: false,
        },
        tooltip: {
          backgroundColor: 'rgba(0, 0, 0, 0.8)',
          padding: 12,
          titleColor: '#fff',
          bodyColor: '#fff',
        }
      }
    }
  })
}

onMounted(() => {
  createUsageChart()
  createQualityChart()
})
</script>

<style scoped>
.transition {
  transition-duration: 200ms;
}
</style>