<template>
  <Layout>
  <div class="min-h-screen bg-white">
  

    <!-- Tab Navigation -->
    <div class="border-b border-gray-200">
      <div class="w-[80%] mx-auto px-8">
        <div class="flex items-center gap-8 overflow-x-auto">
          <button
            v-for="tab in tabs"
            :key="tab.id"
            @click="activeTab = tab.id"
            :class="[
              'py-4 px-2 font-semibold text-sm whitespace-nowrap transition',
              activeTab === tab.id
                ? 'text-gray-900 border-b-2 border-gray-900'
                : 'text-gray-600 hover:text-gray-900'
            ]"
          >
            {{ tab.label }}
          </button>
        </div>
      </div>
    </div>

    <!-- Content Area -->
    <main class="w-[80%] mx-auto px-8 py-16">
      <!-- Overview Tab Content -->
      <div v-show="activeTab === 'overview'" class="space-y-20">
        <div class="bg-white text-slate-700 font-sans antialiased selection:bg-green-100 selection:text-green-800">
    
    <section class="relative overflow-hidden py-16 lg:py-20 w-[90%] mx-auto px-4 sm:px-6 lg:px-8">
      <div class="grid grid-cols-1 lg:grid-cols-12 gap-12 mb-20 items-center">
        <div class="lg:col-span-6 text-left space-y-6">
          <h1 class="text-4xl sm:text-5xl font-semibold text-[#0B1A57] tracking-tight leading-[1.15]">
            SMS API Platform
          </h1>
          <p class="text-base sm:text-lg text-slate-500 font-normal leading-relaxed max-w-lg">
            Programmatically send and receive text messages at scale with powerful SMS APIs. Engage customers worldwide through transactional alerts, OTP verification, notifications, marketing campaigns, and two-way messaging—all with reliable delivery, global coverage, and real-time reporting.
          </p>
          <div class="flex flex-wrap gap-4 pt-2">
            <button class="px-6 py-3 bg-[#24B43C] hover:bg-[#1e9632] text-white font-semibold rounded text-xs tracking-wider uppercase transition duration-150 shadow-sm">
              Get Started Now
            </button>
            <button class="px-6 py-3 border border-slate-300 text-[#0B1A57] hover:bg-slate-50 font-semibold rounded text-xs tracking-wider uppercase transition duration-150">
              Talk to an Expert
            </button>
          </div>
        </div>

        <div class="lg:col-span-6 flex justify-center relative">
          <div class="absolute inset-0 bg-gradient-to-tr from-blue-50/50 to-transparent rounded-full filter blur-3xl -z-10 transform scale-110"></div>
          <div class="w-full max-w-xl bg-slate-900 rounded-xl shadow-2xl overflow-hidden border border-slate-800 p-4 font-mono text-xs text-slate-300">
            <div class="flex items-center gap-2 border-b border-slate-800 pb-3 mb-3">
              <span class="w-3 h-3 rounded-full bg-rose-500"></span>
              <span class="w-3 h-3 rounded-full bg-amber-500"></span>
              <span class="w-3 h-3 rounded-full bg-emerald-500"></span>
              <span class="text-slate-500 ml-2 font-sans">POST /v1/Account/{auth_id}/Message/</span>
            </div>
            <pre class="text-emerald-400 text-lg"><code>{
  <span class="text-sky-400">"message_id"</span>: <span class="text-amber-300">"msg_8f7a92c1"</span>,
  <span class="text-sky-400">"src"</span>: <span class="text-amber-300">"14155550100"</span>,
  <span class="text-sky-400">"dst"</span>: <span class="text-amber-300">"14155550199"</span>,
  <span class="text-sky-400">"text"</span>: <span class="text-amber-300">"Hello World from SMS API!"</span>,
  <span class="text-sky-400">"type"</span>: <span class="text-amber-300">"transactional"</span>,
  <span class="text-sky-400">"encoding"</span>: <span class="text-amber-300">"UTF-8"</span>,
  <span class="text-sky-400">"priority"</span>: <span class="text-amber-300">"high"</span>,
  <span class="text-sky-400">"status"</span>: <span class="text-amber-300">"queued"</span>,
  <span class="text-sky-400">"schedule_at"</span>: <span class="text-amber-300">"2026-06-11T14:30:00Z"</span>,
  <span class="text-sky-400">"callback_url"</span>: <span class="text-amber-300">"https://api.flowdacity.com/webhooks/sms"</span>,
  <span class="text-sky-400">"country"</span>: <span class="text-amber-300">"US"</span>,
  <span class="text-sky-400">"cost"</span>: <span class="text-amber-300">"0.0075"</span>,
  <span class="text-sky-400">"segments"</span>: <span class="text-amber-300">1</span>,
  <span class="text-sky-400">"desc"</span>: <span class="text-amber-300">"Welcome message sent to newly registered customer."</span>
}</code></pre>
          </div>
        </div>
      </div>

      <div class="mt-20 border-t border-slate-100 pt-12">
        <div class="grid grid-cols-2 md:grid-cols-5 gap-8 items-center justify-items-center opacity-40 grayscale">
          <span class="text-lg font-bold tracking-tight text-slate-700">GoDaddy</span>
          <span class="text-xl font-semibold text-slate-700 tracking-wide">workday.</span>
          <span class="text-md font-black text-slate-700 tracking-widest">DECKERS BRANDS</span>
          <span class="text-lg italic font-serif text-slate-700">Greyhound</span>
          <span class="text-xl font-light text-slate-700 tracking-tight">Wix</span>
        </div>
        <p class="text-center text-xs font-semibold text-[#24B43C] mt-10 hover:underline cursor-pointer tracking-wide uppercase flex items-center justify-center gap-1">
          Learn how thousands of innovative businesses rely on Plivo for customer engagement <span>&rarr;</span>
        </p>
      </div>
    </section>

    <section class="bg-slate-900 rounded-xl py-20 border-y border-slate-100">
      <div class="w-[80%] mx-auto px-4 sm:px-6 lg:px-8 text-center">
        <h2 class="text-2xl sm:text-3xl font-semibold text-white mb-4">
          Enable Your App with SMS in Minutes
        </h2>
        <p class="text-slate-500 text-sm max-w-xl mx-auto mb-16">
          Integrate highly interactive core messaging functions directly into your primary database stack.
        </p>

        <div class="grid grid-cols-1 md:grid-cols-2 lg:grid-cols-3 gap-x-8 gap-y-12 text-left max-w-6xl mx-auto">
          <div v-for="(feature, idx) in appFeatures" :key="idx" class="bg-white p-6 rounded-xl border border-slate-100 shadow-sm hover:shadow-md transition-shadow duration-200 space-y-4">
            <div class="w-10 h-10 flex items-center justify-center text-sky-500 bg-sky-50/80 rounded-lg">
              <component :is="feature.icon" class="w-5 h-5" />
            </div>
            <div>
              <h3 class="text-base font-semibold text-[#0B1A57] mb-1.5">{{ feature.title }}</h3>
              <p class="text-xs text-slate-500 leading-relaxed">{{ feature.description }}</p>
            </div>
            <a :href="feature.link" class="inline-flex items-center text-xs font-bold text-[#24B43C] hover:underline pt-1 gap-0.5">
              Learn more <span class="text-sm font-normal">&rarr;</span>
            </a>
          </div>
        </div>
      </div>
    </section>

    <section class="py-20 w-[80%] mx-auto px-4 sm:px-6 lg:px-8 overflow-hidden">
      <div class="grid grid-cols-1 lg:grid-cols-12 gap-12 items-center">
        <div class="lg:col-span-6 flex justify-center relative">
          <div class="absolute inset-0 bg-blue-50/40 rounded-full filter blur-3xl -z-10"></div>
          <div class="w-full max-w-md bg-white border border-slate-100 rounded-2xl p-6 shadow-sm space-y-4">
            <div class="flex justify-between items-center border-b border-slate-50 pb-3">
              <span class="text-xs font-bold text-[#0B1A57] uppercase tracking-wider">Network Status</span>
              <span class="inline-flex items-center gap-1.5 px-2 py-0.5 rounded-full text-[10px] font-medium bg-emerald-50 text-emerald-600">
                <span class="w-1.5 h-1.5 rounded-full bg-emerald-500 animate-pulse"></span> Operational
              </span>
            </div>
            <div class="space-y-2">
              <div class="h-2 bg-slate-400 rounded-full w-full"></div>
              <div class="h-2 bg-slate-400 rounded-full w-5/6"></div>
              <div class="h-2 bg-slate-400 rounded-full w-4/6"></div>
              <div class="h-2 bg-slate-400 rounded-full w-3/6"></div>
              <div class="h-2 bg-slate-400 rounded-full w-2/6"></div>
              <div class="h-2 bg-slate-400 rounded-full w-1/6"></div>
            </div>
          </div>
        </div>

        <div class="lg:col-span-6 space-y-6 lg:pl-8">
          <h2 class="text-2xl sm:text-3xl font-semibold text-[#0B1A57] tracking-tight">
            Global SMS Coverage
          </h2>
          <p class="text-slate-500 text-sm leading-relaxed">
            Connect flawlessly with users across international barriers through a platform configured for performance.
          </p>
          
          <ul class="space-y-4 pt-2">
            <li class="flex items-start gap-3.5">
              <span class="mt-0.5 flex-shrink-0 w-4 h-4 flex items-center justify-center rounded-full bg-sky-50 text-sky-500 text-[10px] font-bold">&checkmark;</span>
              <p class="text-slate-600 text-xs sm:text-sm leading-relaxed">
                Over <span class="font-semibold text-slate-800">190 Countries</span> across North America, Europe, Asia, Oceania, South America and Africa.
              </p>
            </li>
            <li class="flex items-start gap-3.5">
              <span class="mt-0.5 flex-shrink-0 w-4 h-4 flex items-center justify-center rounded-full bg-sky-50 text-sky-500 text-[10px] font-bold">&checkmark;</span>
              <p class="text-slate-600 text-xs sm:text-sm leading-relaxed">
                Receive incoming messages natively in <span class="font-semibold text-slate-800">14 countries</span>.
              </p>
            </li>
            <li class="flex items-start gap-3.5">
              <span class="mt-0.5 flex-shrink-0 w-4 h-4 flex items-center justify-center rounded-full bg-sky-50 text-sky-500 text-[10px] font-bold">&checkmark;</span>
              <p class="text-slate-600 text-xs sm:text-sm leading-relaxed">
                Customize your sender ID in <span class="font-semibold text-slate-800">100 countries</span> outside of US & Canada.
              </p>
            </li>
          </ul>

          <div class="pt-4">
            <button class="px-5 py-2.5 bg-[#24B43C] hover:bg-[#1e9632] text-white font-semibold text-xs tracking-wider uppercase rounded shadow-sm transition duration-150">
              Explore Coverage
            </button>
          </div>
        </div>
      </div>
    </section>

    <section class="bg-slate-50/40 py-20 border-t border-slate-100">
      <div class="w-full mx-auto px-4 sm:px-6 lg:px-8">
        <div class="grid grid-cols-1 lg:grid-cols-12 gap-12 items-start mb-24">
          <div class="lg:col-span-5 space-y-4">
            <h2 class="text-2xl sm:text-3xl font-semibold text-[#0B1A57] leading-tight tracking-tight">
              Powerful Features out of the Box
            </h2>
            <p class="text-slate-500 text-sm max-w-sm">
              Advanced control frameworks ready to process data streams with zero operational friction.
            </p>
            <div class="pt-2">
              <button class="px-5 py-2.5 border border-slate-200 bg-white text-[#0B1A57] hover:bg-slate-50 font-semibold text-xs tracking-wider uppercase rounded shadow-xs transition duration-150">
                View All Features
              </button>
            </div>
          </div>

          <div class="lg:col-span-7 grid grid-cols-1 sm:grid-cols-2 gap-x-6 gap-y-4 bg-white p-8 rounded-2xl border border-slate-100 shadow-xs">
            <div v-for="(item, i) in coreFeatures" :key="i" class="flex items-center gap-3 py-1">
              <span class="w-4 h-4 flex-shrink-0 flex items-center justify-center rounded-full bg-emerald-50 text-[#24B43C] text-[10px] font-bold">&checkmark;</span>
              <span class="text-xs sm:text-sm font-medium text-slate-700">{{ item }}</span>
            </div>
          </div>
        </div>

        <div class="grid grid-cols-1 lg:grid-cols-12 gap-12 w-full items-center pt-8 border-t border-slate-100/70">
          <div class="lg:col-span-6 flex justify-center order-last lg:order-first">
            <div class="w-full  bg-gradient-to-br from-slate-50 to-blue-50/30 rounded-2xl border border-slate-100">
              <img src="@/assets/images/powerpack.png" alt="" class="w-full h-auto">
            </div>
          </div>
          <div class="lg:col-span-6 space-y-6 lg:pl-6">
            <h2 class="text-2xl sm:text-3xl font-semibold text-[#0B1A57] tracking-tight">
              Powerpack for SMS
            </h2>
            <p class="text-xs sm:text-sm text-slate-500 leading-relaxed">
              Experience consistently high SMS delivery and open rates at any volume or send rate with carrier intelligence.
            </p>
            <ul class="space-y-3.5">
              <li v-for="(pItem, pi) in powerpackPoints" :key="pi" class="flex items-center gap-3">
                <span class="w-4 h-4 flex-shrink-0 flex items-center justify-center rounded-full bg-sky-50 text-sky-500 text-[10px] font-bold">&checkmark;</span>
                <span class="text-xs sm:text-sm text-slate-600 font-medium">{{ pItem }}</span>
              </li>
            </ul>
            <div class="pt-2">
              <button class="px-5 py-2.5 bg-[#24B43C] hover:bg-[#1e9632] text-white font-semibold text-xs tracking-wider uppercase rounded shadow-sm transition duration-150">
                Explore Powerpack
              </button>
            </div>
          </div>
        </div>
      </div>
    </section>

    <section class="py-20 w-[80%] mx-auto px-4 sm:px-6 lg:px-8 text-center">
      <h2 class="text-2xl sm:text-3xl font-semibold text-[#0B1A57] mb-4 max-w-2xl mx-auto leading-tight tracking-tight">
        More Ways to Send and Receive SMS Around the World
      </h2>
      <p class="text-slate-400 text-xs sm:text-sm max-w-lg mx-auto mb-16">
        Select alternative message gateway endpoints built for high fallback stability.
      </p>
      
      <div class="grid grid-cols-1 md:grid-cols-3 gap-8 text-left max-w-6xl mx-auto items-start">
        <div class="bg-white border border-slate-100 p-6 rounded-xl shadow-xs space-y-3">
          <div class="text-sky-500 text-lg">📍</div>
          <h3 class="text-sm sm:text-base font-semibold text-[#0B1A57]">Local Phone Numbers</h3>
          <p class="text-xs text-slate-500 leading-relaxed">Use local or mobile phone numbers and send SMS to every country globally. Receive messages on SMS enabled phone numbers in 14 countries.</p>
        </div>
        <div class="bg-white border border-slate-100 p-6 rounded-xl shadow-xs space-y-3">
          <div class="text-sky-500 text-lg">🔏</div>
          <h3 class="text-sm sm:text-base font-semibold text-[#0B1A57]">Alphanumeric Sender ID</h3>
          <p class="text-xs text-slate-500 leading-relaxed">Customize your sender ID to your brand by using alphanumeric characters for your outbound messages in 100 countries outside of US & Canada.</p>
        </div>
        <div class="bg-white border border-slate-100 p-6 rounded-xl shadow-xs space-y-3">
          <div class="text-sky-500 text-lg">📞</div>
          <h3 class="text-sm sm:text-base font-semibold text-[#0B1A57]">Toll Free Numbers</h3>
          <p class="text-xs text-slate-500 leading-relaxed">Send and receive SMS using Toll-free numbers in US & Canada. Buy a new number or enable your existing number to send and receive SMS.</p>
        </div>
      </div>

      <div class="mt-8 max-w-6xl mx-auto grid grid-cols-1 md:grid-cols-3 gap-8 text-left">
        <div class="bg-white border border-slate-100 p-6 rounded-xl shadow-xs space-y-3 md:col-span-1">
          <div class="text-sky-500 text-lg">🔢</div>
          <h3 class="text-sm sm:text-base font-semibold text-[#0B1A57]">Short Code</h3>
          <p class="text-xs text-slate-500 leading-relaxed">Send and receive high throughput and large volume of SMS using Short Codes in the U.S and Canada.</p>
          <a href="#" class="inline-flex items-center text-xs font-bold text-[#24B43C] hover:underline pt-1 gap-0.5">
            Learn More <span class="text-sm font-normal">&rarr;</span>
          </a>
        </div>
        <div class="md:col-span-2 flex items-center justify-center bg-slate-50 rounded-xl p-6 border border-slate-100/70">
          <div class="flex items-center gap-6 text-slate-400 font-sans text-xs">
            <span class="px-3 py-1.5 bg-white rounded shadow-xs font-mono font-bold text-[#0B1A57]">555-01</span>
            <span class="text-slate-400">&mdash;&mdash;&mdash;&mdash;&rarr;</span>
            <span class="text-slate-500 font-medium">Instant High-Volume Delivery Route</span>
          </div>
        </div>
      </div>
    </section>

    <section class="bg-slate-50/50 py-20 border-t border-slate-100">
      <div class="w-[80%] mx-auto px-4 sm:px-6 lg:px-8 text-center">
        <h2 class="text-2xl sm:text-3xl font-semibold text-[#0B1A57] mb-3 tracking-tight">
          Flexible pricing model for your needs
        </h2>
        <p class="text-slate-400 text-xs sm:text-sm max-w-md mx-auto mb-12">
          Pay exclusively for processed data with clear overhead margins.
        </p>

        <div class="grid grid-cols-1 md:grid-cols-2 gap-6 max-w-4xl mx-auto text-left">
          <div class="bg-white p-6 sm:p-8 rounded-xl border border-slate-100 shadow-xs flex items-start gap-5 hover:shadow-md transition-shadow duration-200">
            <div class="w-10 h-10 rounded-lg bg-emerald-50 text-emerald-500 flex items-center justify-center flex-shrink-0 text-lg">💳</div>
            <div class="space-y-1.5">
              <h3 class="text-base font-semibold text-[#0B1A57]">Pay-as-you-go Pricing</h3>
              <p class="text-xs text-slate-500 leading-relaxed">Transparent usage based pricing, discounted from the start.</p>
              <a href="#" class="inline-flex items-center text-xs font-bold text-[#24B43C] hover:underline pt-2 gap-0.5">
                View Pricing <span class="text-sm font-normal">&rarr;</span>
              </a>
            </div>
          </div>
          <div class="bg-white p-6 sm:p-8 rounded-xl border border-slate-100 shadow-xs flex items-start gap-5 hover:shadow-md transition-shadow duration-200">
            <div class="w-10 h-10 rounded-lg bg-emerald-50 text-emerald-500 flex items-center justify-center flex-shrink-0 text-lg">🏷️</div>
            <div class="space-y-1.5">
              <h3 class="text-base font-semibold text-[#0B1A57]">Volume Discounts as You Scale</h3>
              <p class="text-xs text-slate-500 leading-relaxed">Avail additional discounts with committed usage as you scale.</p>
              <a href="#" class="inline-flex items-center text-xs font-bold text-[#24B43C] hover:underline pt-2 gap-0.5">
                Contact Sales <span class="text-sm font-normal">&rarr;</span>
              </a>
            </div>
          </div>
        </div>
      </div>
    </section>

    <section class="py-20 w-[80%] mx-auto px-4 sm:px-6 lg:px-8 text-center">
      <h2 class="text-2xl sm:text-3xl font-semibold text-[#0B1A57] mb-16 tracking-tight">
        Top reasons why businesses choose Plivo
      </h2>

      <div class="grid grid-cols-1 md:grid-cols-2 gap-x-12 gap-y-10 text-left max-w-5xl mx-auto">
        <div class="space-y-2 border-l-2 border-slate-100 pl-4">
          <div class="text-[#24B43C] text-md">🛡️</div>
          <h3 class="text-base font-semibold text-slate-800">Proven Quality and Scale</h3>
          <p class="text-xs text-slate-500 leading-relaxed">With over a billion API requests every month, our globally distributed direct to carrier network and intelligent routing ensures highest SMS delivery and lowest latency for your calls.</p>
        </div>
        <div class="space-y-2 border-l-2 border-slate-100 pl-4">
          <div class="text-[#24B43C] text-md">⚙️</div>
          <h3 class="text-base font-semibold text-slate-800">Enterprise Grade Platform</h3>
          <p class="text-xs text-slate-500 leading-relaxed">Engineered for high availability, extreme reliability and 99.95% uptime SLA. Privacy Shield and GDPR Compliance means any business can trust Plivo with data privacy and security.</p>
        </div>
        <div class="space-y-2 border-l-2 border-slate-100 pl-4">
          <div class="text-[#24B43C] text-md">🎧</div>
          <h3 class="text-base font-semibold text-slate-800">A Team That Truly Cares about Your Success</h3>
          <p class="text-xs text-slate-500 leading-relaxed">Our 24x7 premium support and a consultative customer success team, provide you with all the technical guidance and industry expertise you need, when you need it.</p>
        </div>
        <div class="space-y-2 border-l-2 border-slate-100 pl-4">
          <div class="text-[#24B43C] text-md">💰</div>
          <h3 class="text-base font-semibold text-slate-800">Lower Cost of Ownership</h3>
          <p class="text-xs text-slate-500 leading-relaxed">Receive discounted pricing from the start with simple usage based pricing where you only pay for what you use. Avail additional discounts with committed usage as you scale.</p>
        </div>
      </div>
    </section>

    <section class="bg-slate-900 text-white py-16 text-center rounded-2xl max-w-6xl mx-auto my-12 px-6 shadow-xl relative overflow-hidden">
      <div class="absolute inset-0 bg-[radial-gradient(circle_at_top_right,_var(--tw-gradient-stops))] from-blue-950/40 via-transparent to-transparent pointer-events-none"></div>
      
      <div class="relative z-10 max-w-2xl mx-auto space-y-6">
        <h2 class="text-2xl sm:text-3xl font-semibold tracking-tight text-white">
          It's easy to get started. Sign up for free.
        </h2>
        <p class="text-slate-400 text-xs sm:text-sm font-normal">
          Create your account and receive trial credits or get in touch with our solutions engineers.
        </p>
        <div class="flex flex-wrap items-center justify-center gap-4 pt-4">
          <button class="px-6 py-3 bg-[#24B43C] hover:bg-[#1e9632] text-white font-semibold text-xs tracking-wider uppercase rounded transition duration-150 shadow-md shadow-emerald-950/50">
            GET STARTED NOW
          </button>
          <button class="px-6 py-3 border border-slate-700 text-slate-200 hover:text-white hover:bg-slate-800 font-semibold text-xs tracking-wider uppercase rounded transition duration-150">
            TALK TO AN EXPERT
          </button>
        </div>
      </div>
    </section>

    </div>

       
        
      </div>

      <!-- Features Tab Content -->
      <div v-show="activeTab === 'features'" class="space-y-20">
        <!-- Hero Section -->
        <section class="text-center py-16">
          <h2 class="text-5xl font-bold text-gray-900 mb-4">Features - SMS API Platform</h2>
          <p class="text-xl text-gray-600 mb-8">Powerful SMS functionality for your applications at a global scale</p>
          <div class="flex items-center justify-center gap-4">
            <button class="px-8 py-3 bg-blue-900 text-white font-bold rounded hover:bg-blue-800 transition">
              GET STARTED NOW
            </button>
            <button class="px-8 py-3 border-2 border-gray-900 text-gray-900 font-bold rounded hover:bg-gray-900 hover:text-white transition">
              TALK TO AN EXPERT
            </button>
          </div>
        </section>

        <!-- Essentials Section -->
        <section>
          <div class="flex items-start gap-4 mb-12">
            <h2 class="text-3xl font-bold text-gray-900">Essentials</h2>
            <div class="w-1 h-8 bg-gray-300"></div>
          </div>

          <div class="grid grid-cols-1 md:grid-cols-2 lg:grid-cols-3 gap-8">
            <!-- Essential features -->
            <div class="col-span-1">
              <p class="text-gray-600 leading-relaxed">Essential features already built for you so you can focus on integrating SMS in your application & scale your delivery globally.</p>
            </div>

            <!-- Support for any character set -->
            <div>
              <div class="flex items-start gap-3 mb-4">
                <svg class="w-8 h-8 text-blue-400 flex-shrink-0 mt-1" fill="currentColor" viewBox="0 0 24 24">
                  <text x="50%" y="50%" dominant-baseline="middle" text-anchor="middle" font-size="16" fill="currentColor">aa</text>
                </svg>
              </div>
              <h3 class="text-lg font-bold text-gray-900 mb-2">Support for any character set</h3>
              <p class="text-gray-600">Built in GSM & Unicode character set support to allow any language including Chinese, Arabic and others plus emojis & symbols.</p>
            </div>

            <!-- Long Message Concatenation -->
            <div>
              <div class="flex items-start gap-3 mb-4">
                <svg class="w-8 h-8 text-blue-400 flex-shrink-0 mt-1" fill="currentColor" viewBox="0 0 24 24">
                  <path d="M4 6h16M4 12h16M4 18h16" stroke="currentColor" stroke-width="2" fill="none"/>
                </svg>
              </div>
              <h3 class="text-lg font-bold text-gray-900 mb-2">Long Message Concatenation</h3>
              <p class="text-gray-600">No more split messages. Long messages are automatically concatenated across global networks seamlessly.</p>
            </div>

            <!-- Delivery Report Notifications -->
            <div>
              <div class="flex items-start gap-3 mb-4">
                <svg class="w-8 h-8 text-blue-400 flex-shrink-0 mt-1" fill="currentColor" viewBox="0 0 24 24">
                  <path d="M9 12l2 2 4-4m6 2a9 9 0 11-18 0 9 9 0 0118 0z" />
                </svg>
              </div>
              <h3 class="text-lg font-bold text-gray-900 mb-2">Delivery Report Notifications</h3>
              <p class="text-gray-600">Receive real-time delivery notification of messages sent globally. Track delivery rates and performance of your accounts.</p>
            </div>

            <!-- Message Queuing -->
            <div>
              <div class="flex items-start gap-3 mb-4">
                <svg class="w-8 h-8 text-blue-400 flex-shrink-0 mt-1" fill="currentColor" viewBox="0 0 24 24">
                  <path d="M4 6h16M4 12h16M4 18h16" stroke="currentColor" stroke-width="2" fill="none"/>
                </svg>
              </div>
              <h3 class="text-lg font-bold text-gray-900 mb-2">Message Queuing</h3>
              <p class="text-gray-600">Send multiple SMS in a single API request. We handle the message queuing for you so you don't have to worry about building that.</p>
            </div>

            <!-- MMS Rich-media Support -->
            <div>
              <div class="flex items-start gap-3 mb-4">
                <svg class="w-8 h-8 text-blue-400 flex-shrink-0 mt-1" fill="currentColor" viewBox="0 0 24 24">
                  <path d="M4 16l4.586-4.586a2 2 0 012.828 0L16 16m-2-2l1.586-1.586a2 2 0 012.828 0L20 14m-6-6h.01M6 20h12a2 2 0 002-2V6a2 2 0 00-2-2H6a2 2 0 00-2 2v12a2 2 0 002 2z" />
                </svg>
              </div>
              <h3 class="text-lg font-bold text-gray-900 mb-2">MMS Rich-media Support</h3>
              <p class="text-gray-600">Send and receive photos, gifs, videos and more. Support to send and receive picture messages and SMS in the same phone number.</p>
              <a href="#" class="text-green-600 hover:text-green-700 font-medium text-sm mt-4 inline-block">Learn More →</a>
            </div>
          </div>
        </section>

        <!-- Compliance Section -->
        <section>
          <div class="flex items-start gap-4 mb-12">
            <h2 class="text-3xl font-bold text-gray-900">Compliance</h2>
            <div class="w-1 h-8 bg-gray-300"></div>
          </div>

          <div class="grid grid-cols-1 md:grid-cols-2 lg:grid-cols-3 gap-8">
            <!-- Compliance intro -->
            <div class="col-span-1">
              <p class="text-gray-600 leading-relaxed">Built in local, regulatory and data compliance which frees you up to build your application at scale.</p>
            </div>

            <!-- Message Body Purging -->
            <div>
              <div class="flex items-start gap-3 mb-4">
                <svg class="w-8 h-8 text-blue-400 flex-shrink-0 mt-1" fill="currentColor" viewBox="0 0 24 24">
                  <path d="M9 12l2 2 4-4m6 2a9 9 0 11-18 0 9 9 0 0118 0z" />
                </svg>
              </div>
              <h3 class="text-lg font-bold text-gray-900 mb-2">Message Body Purging</h3>
              <p class="text-gray-600">SMS message content is never stored within any message detail record. By default all debug logs are purged after 30 days.</p>
            </div>

            <!-- Protect Sensitive Data -->
            <div>
              <div class="flex items-start gap-3 mb-4">
                <svg class="w-8 h-8 text-blue-400 flex-shrink-0 mt-1" fill="currentColor" viewBox="0 0 24 24">
                  <path d="M9 12l2 2 4-4m6 2a9 9 0 11-18 0 9 9 0 0118 0z" />
                </svg>
              </div>
              <h3 class="text-lg font-bold text-gray-900 mb-2">Protect Sensitive Data</h3>
              <p class="text-gray-600">Hospitals and other regulated industries use Plivo globally. Disable logging and mask phone numbers to protect for such use cases.</p>
            </div>

            <!-- Smart Rate Limiting -->
            <div>
              <div class="flex items-start gap-3 mb-4">
                <svg class="w-8 h-8 text-blue-400 flex-shrink-0 mt-1" fill="currentColor" viewBox="0 0 24 24">
                  <path d="M9 12l2 2 4-4m6 2a9 9 0 11-18 0 9 9 0 0118 0z" />
                </svg>
              </div>
              <h3 class="text-lg font-bold text-gray-900 mb-2">Smart Rate Limiting</h3>
              <p class="text-gray-600">Stay compliant with messaging frequency and throughput regulations per source number in each country.</p>
            </div>

            <!-- Automatic Opt-out Handling -->
            <div>
              <div class="flex items-start gap-3 mb-4">
                <svg class="w-8 h-8 text-blue-400 flex-shrink-0 mt-1" fill="currentColor" viewBox="0 0 24 24">
                  <path d="M9 12l2 2 4-4m6 2a9 9 0 11-18 0 9 9 0 0118 0z" />
                </svg>
              </div>
              <h3 class="text-lg font-bold text-gray-900 mb-2">Automatic Opt-out Handling</h3>
              <p class="text-gray-600">Replies such as "Stop", "Cancel" are automatically handled for you on long codes. Plivo manages the opt-outs in such cases.</p>
            </div>
          </div>
        </section>

        <!-- Improved Message Delivery Section -->
        <section>
          <div class="flex items-start gap-4 mb-12">
            <h2 class="text-3xl font-bold text-gray-900">Improved<br/>Message Delivery</h2>
            <div class="w-1 h-8 bg-gray-300"></div>
          </div>

          <div class="grid grid-cols-1 md:grid-cols-2 lg:grid-cols-3 gap-8">
            <!-- Delivery intro -->
            <div class="col-span-1">
              <p class="text-gray-600 leading-relaxed">Quality based routing engine and other features to ensure the best deliverability across 200 countries.</p>
            </div>

            <!-- Intelligent Message Encoding -->
            <div>
              <div class="flex items-start gap-3 mb-4">
                <svg class="w-8 h-8 text-blue-400 flex-shrink-0 mt-1" fill="currentColor" viewBox="0 0 24 24">
                  <path d="M4 6h16M4 12h16M4 18h16" stroke="currentColor" stroke-width="2" fill="none"/>
                </svg>
              </div>
              <h3 class="text-lg font-bold text-gray-900 mb-2">Intelligent Message Encoding</h3>
              <p class="text-gray-600">Plivo replaces unicode characters with similar gsm characters to ensure message delivery to destination networks that don't support unicode.</p>
            </div>

            <!-- Number Pooling -->
            <div>
              <div class="flex items-start gap-3 mb-4">
                <svg class="w-8 h-8 text-blue-400 flex-shrink-0 mt-1" fill="currentColor" viewBox="0 0 24 24">
                  <path d="M4 6h16M4 12h16M4 18h16" stroke="currentColor" stroke-width="2" fill="none"/>
                </svg>
              </div>
              <h3 class="text-lg font-bold text-gray-900 mb-2">Number Pooling</h3>
              <p class="text-gray-600">Improve delivery rate by spreading your messages across a pool of phone numbers to reach your users in time.</p>
            </div>

            <!-- Conversion API -->
            <div>
              <div class="flex items-start gap-3 mb-4">
                <svg class="w-8 h-8 text-blue-400 flex-shrink-0 mt-1" fill="currentColor" viewBox="0 0 24 24">
                  <path d="M9 12l2 2 4-4m6 2a9 9 0 11-18 0 9 9 0 0118 0z" />
                </svg>
              </div>
              <h3 class="text-lg font-bold text-gray-900 mb-2">Conversion API</h3>
              <p class="text-gray-600">Real time feedback from your application allows Plivo's self adjusting quality based routing engine to ensures best delivery.</p>
            </div>

            <!-- Local Match -->
            <div>
              <div class="flex items-start gap-3 mb-4">
                <svg class="w-8 h-8 text-blue-400 flex-shrink-0 mt-1" fill="currentColor" viewBox="0 0 24 24">
                  <path d="M9 12l2 2 4-4m6 2a9 9 0 11-18 0 9 9 0 0118 0z" />
                </svg>
              </div>
              <h3 class="text-lg font-bold text-gray-900 mb-2">Local Match</h3>
              <p class="text-gray-600">To improve read rates, auto select a local area number as the sender id for each user from a pool of numbers.</p>
            </div>
          </div>
        </section>

        <!-- Faster Time to Market Section -->
        <section class="py-16">
          <h2 class="text-4xl font-bold text-gray-900 text-center mb-4">Faster Time to Market</h2>
          <p class="text-center text-gray-600 max-w-3xl mx-auto mb-16">Build, Integrate and troubleshoot issues faster. With Plivo focus on building the features that differentiates you and be faster to the market.</p>

          <div class="grid grid-cols-1 lg:grid-cols-2 gap-12 items-start">
            <!-- Left side - Features list -->
            <div class="space-y-6">
              <div class="flex items-start gap-4">
                <svg class="w-6 h-6 text-blue-400 flex-shrink-0 mt-1" fill="currentColor" viewBox="0 0 20 20">
                  <path fill-rule="evenodd" d="M16.707 5.293a1 1 0 010 1.414l-8 8a1 1 0 01-1.414 0l-4-4a1 1 0 011.414-1.414L8 12.586l7.293-7.293a1 1 0 011.414 0z" clip-rule="evenodd" />
                </svg>
                <div>
                  <h3 class="text-lg font-bold text-gray-900 mb-1">Sticky Sender</h3>
                  <p class="text-gray-600">Interact with customers using the same recognizable phone number or sender ID to ensure a better experience.</p>
                </div>
              </div>

              <div class="flex items-start gap-4">
                <svg class="w-6 h-6 text-blue-400 flex-shrink-0 mt-1" fill="currentColor" viewBox="0 0 20 20">
                  <path fill-rule="evenodd" d="M16.707 5.293a1 1 0 010 1.414l-8 8a1 1 0 01-1.414 0l-4-4a1 1 0 011.414-1.414L8 12.586l7.293-7.293a1 1 0 011.414 0z" clip-rule="evenodd" />
                </svg>
                <div>
                  <h3 class="text-lg font-bold text-gray-900 mb-1">Built in Multi-tenancy</h3>
                  <p class="text-gray-600">Segment your customers based on use case, spend capacity or risk profile and track usage and billing with Sub-Accounts.</p>
                </div>
              </div>

              <div class="flex items-start gap-4">
                <svg class="w-6 h-6 text-blue-400 flex-shrink-0 mt-1" fill="currentColor" viewBox="0 0 20 20">
                  <path fill-rule="evenodd" d="M16.707 5.293a1 1 0 010 1.414l-8 8a1 1 0 01-1.414 0l-4-4a1 1 0 011.414-1.414L8 12.586l7.293-7.293a1 1 0 011.414 0z" clip-rule="evenodd" />
                </svg>
                <div>
                  <h3 class="text-lg font-bold text-gray-900 mb-1">Detailed Debug Logs</h3>
                  <p class="text-gray-600">Debug and troubleshoot issues and problems faster with detailed logs. Drill down to the details to find the root cause.</p>
                </div>
              </div>
            </div>

            <!-- Right side - Illustration and more features -->
            <div class="space-y-6">
              <div class="bg-gradient-to-br from-blue-50 to-blue-100 rounded-lg p-8 h-64 flex items-center justify-center">
                <p class="text-gray-500 text-center">Developer Tools Illustration</p>
              </div>

              <div class="flex items-start gap-4">
                <svg class="w-6 h-6 text-blue-400 flex-shrink-0 mt-1" fill="currentColor" viewBox="0 0 20 20">
                  <path fill-rule="evenodd" d="M16.707 5.293a1 1 0 010 1.414l-8 8a1 1 0 01-1.414 0l-4-4a1 1 0 011.414-1.414L8 12.586l7.293-7.293a1 1 0 011.414 0z" clip-rule="evenodd" />
                </svg>
                <div>
                  <h3 class="text-lg font-bold text-gray-900 mb-1">Extensive Documentation</h3>
                  <p class="text-gray-600">With our detailed documentation and sample code get started in minutes. Just copy paste code samples in most cases.</p>
                </div>
              </div>

              <div class="flex items-start gap-4">
                <svg class="w-6 h-6 text-blue-400 flex-shrink-0 mt-1" fill="currentColor" viewBox="0 0 20 20">
                  <path fill-rule="evenodd" d="M16.707 5.293a1 1 0 010 1.414l-8 8a1 1 0 01-1.414 0l-4-4a1 1 0 011.414-1.414L8 12.586l7.293-7.293a1 1 0 011.414 0z" clip-rule="evenodd" />
                </svg>
                <div>
                  <h3 class="text-lg font-bold text-gray-900 mb-1">Server Side SDKs</h3>
                  <p class="text-gray-600">Program in your web language of choice with our server side SDKs in Java, C#, Python, Ruby, Nodejs or Golang.</p>
                </div>
              </div>

              <div class="flex items-start gap-4">
                <svg class="w-6 h-6 text-blue-400 flex-shrink-0 mt-1" fill="currentColor" viewBox="0 0 20 20">
                  <path fill-rule="evenodd" d="M16.707 5.293a1 1 0 010 1.414l-8 8a1 1 0 01-1.414 0l-4-4a1 1 0 011.414-1.414L8 12.586l7.293-7.293a1 1 0 011.414 0z" clip-rule="evenodd" />
                </svg>
                <div>
                  <h3 class="text-lg font-bold text-gray-900 mb-1">Reusable Templates</h3>
                  <p class="text-gray-600">With a vast library of ready to use templates you can add powerful functionality quickly by writing minimal code.</p>
                </div>
              </div>
            </div>
          </div>
        </section>

        <!-- CTA Section -->
        <section class="text-center py-16">
          <h2 class="text-4xl font-bold text-gray-900 mb-4">It's easy to get started. Sign up for free.</h2>
          <p class="text-gray-600 mb-8">Create your account and receive trial credits or get in touch with us</p>
          <div class="flex items-center justify-center gap-4">
            <button class="px-8 py-3 bg-green-600 text-white font-bold rounded hover:bg-green-700 transition">
              GET STARTED NOW
            </button>
            <button class="px-8 py-3 border-2 border-green-600 text-green-600 font-bold rounded hover:bg-green-600 hover:text-white transition">
              TALK TO AN EXPERT
            </button>
          </div>
        </section>
      </div>
    </main>

   
  </div>

</Layout>
</template>

<script setup>
import { ref, shallowRef } from 'vue'

const activeTab = ref('overview')

const tabs = [
  { id: 'overview', label: 'OVERVIEW' },
  { id: 'features', label: 'FEATURES' },
  { id: 'coverage', label: 'COVERAGE' },
  { id: 'shortcode', label: 'SHORT CODE' },
  { id: 'tollfree', label: 'TOLL-FREE' },
  { id: 'mms', label: 'MMS' },
  { id: 'powerpack', label: 'POWERPACK' },
  { id: 'pricing', label: 'PRICING' }
]

const ShieldIcon = { template: '<span>🛡️</span>' }
const BellIcon = { template: '<span>🔔</span>' }
const MegaphoneIcon = { template: '<span>📢</span>' }
const SurveyIcon = { template: '<span>📝</span>' }
const ReplyIcon = { template: '<span>↩️</span>' }
const ClockIcon = { template: '<span>⏰</span>' }

const appFeatures = ref([
  {
    title: 'Two-factor authentication',
    description: 'Secure your applications at scale by sending dynamic verification codes.',
    link: '#',
    icon: shallowRef(ShieldIcon)
  },
  {
    title: 'Alerts and Notification',
    description: 'Send automated account alerts, dispatch notifications or reminders.',
    link: '#',
    icon: shallowRef(BellIcon)
  },
  {
    title: 'SMS Marketing',
    description: 'Engage with prospects and customers throughout their entire journey.',
    link: '#',
    icon: shallowRef(MegaphoneIcon)
  },
  {
    title: 'SMS Survey',
    description: 'Send and receive SMS, and conduct Surveys.',
    link: '#',
    icon: shallowRef(SurveyIcon)
  },
  {
    title: 'SMS Autoresponder',
    description: 'Automatically respond to your customers while you are away.',
    link: '#',
    icon: shallowRef(ReplyIcon)
  },
  {
    title: 'Appointment Reminders',
    description: 'Reduce no-shows by sending automated reminder sms from your systems.',
    link: '#',
    icon: shallowRef(ClockIcon)
  }
])

const coreFeatures = ref([
  'Long Message Concatenation',
  'Handle opt out Intent',
  'Support for any Character Set',
  'Message Queueing',
  'Default Message Body Purging',
  'Number Pooling',
  'Message Feedback API',
  'Sticky Sender'
])

const powerpackPoints = ref([
  'Great delivery even at high scale',
  'Local Connect for higher open rates',
  'Smart Queueing for carrier compliance',
  'Consistent experience for your end users'
])
</script>

<style scoped>
button {
  transition: all 0.2s ease;
}
</style>