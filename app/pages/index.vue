<template>
  <Layout>
    <section class="relative bg-slate-950 text-white min-h-screen flex items-center pt-24 pb-16 overflow-hidden">
      <div class="absolute top-0 left-1/4 w-96 h-96 bg-blue-600/10 rounded-full blur-[120px] pointer-events-none"></div>
      <div class="absolute bottom-10 right-1/4 w-96 h-96 bg-emerald-500/10 rounded-full blur-[120px] pointer-events-none"></div>

      <div class="max-w-7xl mx-auto px-6 lg:px-8 w-full grid grid-cols-1 lg:grid-cols-12 gap-12 lg:gap-8 items-center">
        <div class="lg:col-span-6 space-y-6 text-center lg:text-left z-10">
          <a href="#" class="inline-flex items-center gap-2 bg-emerald-500/10 border border-emerald-500/30 text-emerald-400 px-4 py-1.5 rounded-full text-xs font-semibold tracking-wide uppercase hover:bg-emerald-500/20 transition-all duration-300">
            <span class="flex h-2 w-2 relative">
              <span class="animate-ping absolute inline-flex h-full w-full rounded-full bg-emerald-400 opacity-75"></span>
              <span class="relative inline-flex rounded-full h-2 w-2 bg-emerald-500"></span>
            </span>
            🆕 Zentrunk — Next-Gen SIP Trunking
          </a>

          <h1 class="text-4xl sm:text-5xl lg:text-6xl font-extrabold tracking-tight bg-gradient-to-r from-white via-slate-200 to-slate-400 bg-clip-text text-transparent leading-[1.15]">
            Connect and engage with your customers globally
          </h1>
          
          <p class="text-lg sm:text-xl text-slate-400 max-w-2xl mx-auto lg:mx-0 font-light leading-relaxed">
            Flowdacity's programmable voice and messaging platform empowers builders to engineer flawless, real-time customer experiences at scale.
          </p>

          <div class="flex flex-col sm:flex-row gap-4 justify-center lg:justify-start pt-4">
            <button class="px-8 py-4 bg-blue-600 hover:bg-blue-500 text-white font-semibold rounded-lg shadow-lg shadow-blue-600/20 active:scale-[0.98] transition-all duration-200">
              Get Started Now
            </button>
            <button class="px-8 py-4 bg-slate-900 hover:bg-slate-800 text-slate-200 border border-slate-800 font-semibold rounded-lg active:scale-[0.98] transition-all duration-200">
              Talk to an Expert
            </button>
          </div>
        </div>

        <div class="lg:col-span-6 relative w-full flex justify-center items-center">
          <div class="relative w-full max-w-[580px] aspect-square bg-gradient-to-tr from-blue-600/20 to-emerald-500/20 rounded-2xl border border-slate-800/80 backdrop-blur-sm p-6 flex items-center justify-center group overflow-hidden shadow-2xl">
            <img class="w-full h-full object-contain transform group-hover:scale-105 transition-transform duration-700 ease-out" src="@/assets/images/partner.png" alt="Flowdacity Platform Flow Interface">
          </div>
        </div>
      </div>
    </section>

    <section class="bg-slate-900 border-y border-slate-800/60 py-12 px-6">
      <div class="max-w-7xl mx-auto">
        <p class="text-center text-xs font-semibold uppercase tracking-widest text-slate-500 mb-8">
          Trusted by engineering & product teams globally
        </p>
        <div class="grid grid-cols-2 sm:grid-cols-4 lg:grid-cols-8 gap-y-8 gap-x-6 items-center justify-items-center opacity-60">
          <div class="text-slate-300 font-extrabold tracking-tight text-xl hover:text-white transition cursor-default">IBM</div>
          <div class="text-slate-300 font-extrabold tracking-tight text-xl hover:text-white transition cursor-default">GoDaddy</div>
          <div class="text-slate-300 font-extrabold tracking-tight text-xl hover:text-white transition cursor-default">SnapCall</div>
          <div class="text-slate-300 font-extrabold tracking-tight text-xl hover:text-white transition cursor-default">Grayblind</div>
          <div class="text-slate-300 font-extrabold tracking-tight text-xl hover:text-white transition cursor-default">OLA</div>
          <div class="text-slate-300 font-extrabold tracking-tight text-xl hover:text-white transition cursor-default">GOJEK</div>
          <div class="text-slate-300 font-extrabold tracking-tight text-xl hover:text-white transition cursor-default">PagerDuty</div>
          <div class="text-slate-300 font-extrabold tracking-tight text-xl hover:text-white transition cursor-default">Lifesize</div>
        </div>
        <div class="text-center mt-10">
          <a href="#" class="inline-flex items-center gap-1.5 text-sm font-medium text-emerald-400 hover:text-emerald-300 transition-colors group">
            See how innovative teams scale with Flowdacity 
            <span class="transform group-hover:translate-x-1 transition-transform">→</span>
          </a>
        </div>
      </div>
    </section>

    <section class="bg-slate-50 py-24 px-6 border-b border-slate-100">
      <div class="max-w-3xl mx-auto text-center">
        <h2 class="text-3xl sm:text-4xl font-bold tracking-tight text-slate-900 mb-4">
          An enterprise-grade cloud communications stack built for developers
        </h2>
        <p class="text-lg text-slate-600 font-light">
          Global delivery pipelines, elastic infrastructure, and comprehensive APIs that seamlessly blend into your existing codebase.
        </p>
      </div>
    </section>

    <section class="bg-white py-24 px-6">
      <div class="max-w-7xl mx-auto">
        <div class="bg-gradient-to-r from-slate-900 to-slate-950 text-white p-8 sm:p-12 rounded-2xl mb-12 flex flex-col md:flex-row items-start md:items-center justify-between gap-6 border border-slate-800 shadow-xl relative overflow-hidden group">
          <div class="absolute top-0 right-0 w-64 h-64 bg-blue-600/10 rounded-full blur-3xl pointer-events-none"></div>
          
          <div class="flex flex-col sm:flex-row items-start gap-5">
            <div class="p-3 bg-blue-500/10 border border-blue-500/20 rounded-xl text-blue-400 text-3xl shrink-0">
              ⚡
            </div>
            <div>
              <div class="flex items-center gap-2.5 mb-1">
                <h3 class="text-2xl font-bold tracking-tight">PHLO Workflow Engine</h3>
                <span class="text-[10px] uppercase font-bold tracking-wider bg-blue-500 text-white px-2 py-0.5 rounded">Visual Builder</span>
              </div>
              <p class="text-slate-400 max-w-xl text-base font-light">
                Drag, drop, and deploy visual communication maps instantly. Orchestrate complex calling and message conditional pipelines without writing backend loops.
              </p>
            </div>
          </div>
          <a href="#" class="inline-flex items-center gap-1 shrink-0 font-medium text-emerald-400 hover:text-emerald-300 transition group mt-2 md:mt-0">
            Explore Visual Workflows <span class="transform group-hover:translate-x-1 transition-transform">→</span>
          </a>
        </div>

        <div class="grid grid-cols-1 md:grid-cols-2 gap-8">
          <div class="bg-slate-50/60 border border-slate-200/60 rounded-xl p-8 hover:bg-white hover:shadow-xl hover:border-transparent transition-all duration-300 flex flex-col justify-between group">
            <div>
              <div class="w-12 h-12 flex items-center justify-center bg-white rounded-lg shadow-sm text-2xl mb-6 border border-slate-100 group-hover:scale-110 transition-transform">
                💬
              </div>
              <h3 class="text-xl font-bold text-slate-900 mb-2">SMS API Platform</h3>
              <p class="text-slate-600 text-sm leading-relaxed mb-6 font-light">
                Programmatically transmit alerts, identity security notifications, and structural interactions to over 190 countries with ultra-low latencies.
              </p>
            </div>
            <a href="#" class="text-sm font-semibold text-blue-600 hover:text-blue-700 inline-flex items-center gap-1 group">
              API Reference <span class="transform group-hover:translate-x-0.5 transition-transform">→</span>
            </a>
          </div>

          <div class="bg-slate-50/60 border border-slate-200/60 rounded-xl p-8 hover:bg-white hover:shadow-xl hover:border-transparent transition-all duration-300 flex flex-col justify-between group">
            <div>
              <div class="w-12 h-12 flex items-center justify-center bg-white rounded-lg shadow-sm text-2xl mb-6 border border-slate-100 group-hover:scale-110 transition-transform">
                📞
              </div>
              <h3 class="text-xl font-bold text-slate-900 mb-2">Voice API Platform</h3>
              <p class="text-slate-600 text-sm leading-relaxed mb-6 font-light">
                Inject powerful crystal-clear conversational capabilities, automated interactive responses, and audio features directly into cloud native applications.
              </p>
            </div>
            <a href="#" class="text-sm font-semibold text-blue-600 hover:text-blue-700 inline-flex items-center gap-1 group">
              API Reference <span class="transform group-hover:translate-x-0.5 transition-transform">→</span>
            </a>
          </div>

          <div class="bg-slate-50/60 border border-slate-200/60 rounded-xl p-8 hover:bg-white hover:shadow-xl hover:border-transparent transition-all duration-300 flex flex-col justify-between group">
            <div>
              <div class="w-12 h-12 flex items-center justify-center bg-white rounded-lg shadow-sm text-2xl mb-6 border border-slate-100 group-hover:scale-110 transition-transform relative">
                ☎️
                <span class="absolute -top-1.5 -right-1.5 flex h-2 w-2">
                  <span class="animate-ping absolute inline-flex h-full w-full rounded-full bg-emerald-400 opacity-75"></span>
                  <span class="relative inline-flex rounded-full h-2 w-2 bg-emerald-500"></span>
                </span>
              </div>
              <div class="flex items-center gap-2 mb-2">
                <h3 class="text-xl font-bold text-slate-900">Zentrunk SIP</h3>
                <span class="text-[9px] uppercase font-bold tracking-wider bg-emerald-100 text-emerald-800 px-2 py-0.5 rounded">New Release</span>
              </div>
              <p class="text-slate-600 text-sm leading-relaxed mb-6 font-light">
                Elastically scale native communication frameworks. Deploy cloud-based cloud SIP trunks to merge physical legacy systems with distributed voice.
              </p>
            </div>
            <a href="#" class="text-sm font-semibold text-blue-600 hover:text-blue-700 inline-flex items-center gap-1 group">
              Trunk Configuration <span class="transform group-hover:translate-x-0.5 transition-transform">→</span>
            </a>
          </div>

          <div class="bg-slate-50/60 border border-slate-200/60 rounded-xl p-8 hover:bg-white hover:shadow-xl hover:border-transparent transition-all duration-300 flex flex-col justify-between group">
            <div>
              <div class="w-12 h-12 flex items-center justify-center bg-white rounded-lg shadow-sm text-2xl mb-6 border border-slate-100 group-hover:scale-110 transition-transform">
                🔢
              </div>
              <h3 class="text-xl font-bold text-slate-900 mb-2">Global Numbers</h3>
              <p class="text-slate-600 text-sm leading-relaxed mb-6 font-light">
                Query, claim, and immediately provision local, mobile, virtual, and high-volume toll-free communication endpoints worldwide via simple API parameters.
              </p>
            </div>
            <a href="#" class="text-sm font-semibold text-blue-600 hover:text-blue-700 inline-flex items-center gap-1 group">
              Inventory Access <span class="transform group-hover:translate-x-0.5 transition-transform">→</span>
            </a>
          </div>
        </div>
      </div>
    </section>

    <section class="bg-slate-50 py-24 px-6 border-y border-slate-200/60">
      <div class="max-w-7xl mx-auto">
        <div class="text-center max-w-2xl mx-auto mb-16">
          <h2 class="text-3xl font-bold tracking-tight text-slate-900 mb-3">Pre-engineered solution templates</h2>
          <p class="text-slate-600 font-light">Accelerate development cycles using ready-made reference architectures optimized for performance.</p>
        </div>

        <div class="grid grid-cols-1 md:grid-cols-3 gap-8">
          <div class="bg-white rounded-xl border border-slate-200/60 p-8 shadow-sm hover:shadow-md transition-shadow">
            <div class="w-10 h-10 flex items-center justify-center bg-emerald-50 text-emerald-600 rounded-lg text-lg font-bold mb-6">
              ✓
            </div>
            <h3 class="text-lg font-bold text-slate-900 mb-2">Two-Factor Auth (2FA)</h3>
            <p class="text-slate-600 text-sm font-light leading-relaxed mb-6">
              Mitigate systemic compromise risk vectors by instantly validating user identities with dynamic token streams sent via automated voice or SMS hooks.
            </p>
            <a href="#" class="text-xs font-semibold tracking-wider text-slate-900 uppercase hover:text-blue-600 transition">View Guide</a>
          </div>

          <div class="bg-white rounded-xl border border-slate-200/60 p-8 shadow-sm hover:shadow-md transition-shadow">
            <div class="w-10 h-10 flex items-center justify-center bg-blue-50 text-blue-600 rounded-lg text-lg font-bold mb-6">
              📊
            </div>
            <h3 class="text-lg font-bold text-slate-900 mb-2">Conversion Call Tracking</h3>
            <p class="text-slate-600 text-sm font-light leading-relaxed mb-6">
              Isolate performance metrics. Map call conversions natively to calculate digital and offline marketing multi-touch attribution campaigns accurately.
            </p>
            <a href="#" class="text-xs font-semibold tracking-wider text-slate-900 uppercase hover:text-blue-600 transition">View Guide</a>
          </div>

          <div class="bg-white rounded-xl border border-slate-200/60 p-8 shadow-sm hover:shadow-md transition-shadow">
            <div class="w-10 h-10 flex items-center justify-center bg-amber-50 text-amber-600 rounded-lg text-lg font-bold mb-6">
              🔔
            </div>
            <h3 class="text-lg font-bold text-slate-900 mb-2">Automated Notifications</h3>
            <p class="text-slate-600 text-sm font-light leading-relaxed mb-6">
              Broadcast critical service announcements, transactional shipping dispatches, security notifications, or targeted event reminders safely.
            </p>
            <a href="#" class="text-xs font-semibold tracking-wider text-slate-900 uppercase hover:text-blue-600 transition">View Guide</a>
          </div>
        </div>
      </div>
    </section>

    <section class="bg-white py-28 px-6 text-center relative overflow-hidden">
      <div class="absolute top-1/2 left-1/2 -translate-x-1/2 -translate-y-1/2 w-[600px] h-[600px] bg-emerald-500/5 rounded-full blur-3xl pointer-events-none"></div>
      
      <div class="max-w-3xl mx-auto relative z-10 space-y-6">
        <h2 class="text-4xl font-extrabold tracking-tight text-slate-900 sm:text-5xl">
          Build the future of engagement. <br class="hidden sm:inline" />Start building today.
        </h2>
        <p class="text-lg text-slate-600 max-w-xl mx-auto font-light leading-relaxed">
          Create your developer Sandbox instance now to access free platform test credits. No hidden commitments or upfront infrastructure fees.
        </p>

        <div class="flex flex-col sm:flex-row gap-4 justify-center pt-6">
          <button class="px-8 py-4 bg-emerald-600 hover:bg-emerald-500 text-white font-semibold rounded-lg shadow-lg shadow-emerald-600/20 active:scale-[0.98] transition-all duration-200">
            Create Free Account
          </button>
          <button class="px-8 py-4 bg-white hover:bg-slate-50 text-slate-800 border border-slate-300 font-semibold rounded-lg active:scale-[0.98] transition-all duration-200">
            Contact Sales Architecture
          </button>
        </div>
      </div>
    </section>
  </Layout>
</template>

<script setup>
import Layout from '../components/Layout.vue'
</script>

<style scoped>
/* Minor aesthetic enhancements complementing global Tailwind configurations */
section {
  content-visibility: auto;
}
</style>