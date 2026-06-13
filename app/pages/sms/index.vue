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
          Learn how thousands of innovative businesses rely on Flowdacity for customer engagement <span>&rarr;</span>
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
        Top reasons why businesses choose Flowdacity
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
          <p class="text-xs text-slate-500 leading-relaxed">Engineered for high availability, extreme reliability and 99.95% uptime SLA. Privacy Shield and GDPR Compliance means any business can trust Flowdacity with data privacy and security.</p>
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
          <div class="bg-white text-slate-700 font-sans antialiased selection:bg-green-100 selection:text-green-800">

    <section class="text-center py-20 max-w-4xl mx-auto px-4 space-y-5">
      <h1 class="text-4xl sm:text-5xl font-semibold text-[#0B1A57] tracking-tight leading-[1.15]">
        Features - SMS API Platform
      </h1>
      <p class="text-base sm:text-lg text-slate-500 max-w-2xl mx-auto leading-relaxed">
        Powerful SMS functionality for your applications at a global scale. Elevate your delivery mechanics with unified developer frameworks.
      </p>
      <div class="flex flex-wrap items-center justify-center gap-4 pt-4">
        <button class="px-6 py-3 bg-[#0B1A57] hover:bg-[#060e33] text-white font-semibold text-xs tracking-wider uppercase rounded transition duration-150 shadow-sm">
          Get Started Now
        </button>
        <button class="px-6 py-3 border border-slate-300 text-[#0B1A57] hover:bg-slate-50 font-semibold text-xs tracking-wider uppercase rounded transition duration-150">
          Talk to an Expert
        </button>
      </div>
    </section>

    <section class="py-16 border-t border-slate-100 max-w-7xl mx-auto px-4 sm:px-6 lg:px-8">
      <div class="grid grid-cols-1 lg:grid-cols-12 gap-12 items-start">
        
        <div class="lg:col-span-4 space-y-4 lg:sticky lg:top-6">
          <div class="flex items-center gap-3">
            <h2 class="text-2xl font-semibold text-[#0B1A57] tracking-tight">Essentials</h2>
            <div class="w-[2px] h-6 bg-slate-200"></div>
          </div>
          <p class="text-xs sm:text-sm text-slate-500 leading-relaxed pr-4">
            Essential features already built for you so you can focus on integrating SMS in your application & scale your delivery globally.
          </p>
        </div>

        <div class="lg:col-span-8 grid grid-cols-1 sm:grid-cols-2 gap-x-8 gap-y-12">
          
          <div class="space-y-3">
            <div class="w-9 h-9 flex items-center justify-center rounded-lg bg-sky-50 text-sky-500 border border-sky-100/30">
              <span class="text-xs font-mono font-bold tracking-tight">aa</span>
            </div>
            <h3 class="text-sm font-semibold text-[#0B1A57]">Support for any character set</h3>
            <p class="text-xs text-slate-500 leading-relaxed">
              Built-in GSM & Unicode character set support to allow any language including Chinese, Arabic, and others plus emojis & symbols seamlessly.
            </p>
          </div>

          <div class="space-y-3">
            <div class="w-9 h-9 flex items-center justify-center rounded-lg bg-sky-50 text-sky-500">
              <svg class="w-4 h-4" fill="none" stroke="currentColor" stroke-width="2.5" viewBox="0 0 24 24">
                <path stroke-linecap="round" stroke-linejoin="round" d="M4 6h16M4 12h16M4 18h16" />
              </svg>
            </div>
            <h3 class="text-sm font-semibold text-[#0B1A57]">Long Message Concatenation</h3>
            <p class="text-xs text-slate-500 leading-relaxed">
              No more split messages. Long text contents are automatically concatenated across global telecom networks natively.
            </p>
          </div>

          <div class="space-y-3">
            <div class="w-9 h-9 flex items-center justify-center rounded-lg bg-sky-50 text-sky-500">
              <svg class="w-4 h-4" fill="none" stroke="currentColor" stroke-width="2.5" viewBox="0 0 24 24">
                <path stroke-linecap="round" stroke-linejoin="round" d="M9 12l2 2 4-4m6 2a9 9 0 11-18 0 9 9 0 0118 0z" />
              </svg>
            </div>
            <h3 class="text-sm font-semibold text-[#0B1A57]">Delivery Report Notifications</h3>
            <p class="text-xs text-slate-500 leading-relaxed">
              Receive real-time delivery notification of messages sent globally. Track performance and network status logs instantly.
            </p>
          </div>

          <div class="space-y-3">
            <div class="w-9 h-9 flex items-center justify-center rounded-lg bg-sky-50 text-sky-500">
              <svg class="w-4 h-4" fill="none" stroke="currentColor" stroke-width="2.5" viewBox="0 0 24 24">
                <path stroke-linecap="round" stroke-linejoin="round" d="M19 11H5m14 0a2 2 0 012 2v6a2 2 0 01-2 2H5a2 2 0 01-2-2v-6a2 2 0 012-2m14 0V9a2 2 0 00-2-2M5 11V9a2 2 0 012-2m0 0V5a2 2 0 012-2h6a2 2 0 012 2v2M7 7h10" />
              </svg>
            </div>
            <h3 class="text-sm font-semibold text-[#0B1A57]">Message Queuing</h3>
            <p class="text-xs text-slate-500 leading-relaxed">
              Send multiple SMS in a single API request call. We manage concurrent processing tasks so your microservices stay clean.
            </p>
          </div>

          <div class="space-y-3 sm:col-span-2 bg-slate-50/50 p-5 rounded-xl border border-slate-100">
            <div class="w-9 h-9 flex items-center justify-center rounded-lg bg-sky-50 text-sky-500">
              <svg class="w-4 h-4" fill="none" stroke="currentColor" stroke-width="2.5" viewBox="0 0 24 24">
                <path stroke-linecap="round" stroke-linejoin="round" d="M4 16l4.586-4.586a2 2 0 012.828 0L16 16m-2-2l1.586-1.586a2 2 0 012.828 0L20 14m-6-6h.01M6 20h12a2 2 0 002-2V6a2 2 0 00-2-2H6a2 2 0 00-2 2v12a2 2 0 002 2z" />
              </svg>
            </div>
            <h3 class="text-sm font-semibold text-[#0B1A57]">MMS Rich-media Support</h3>
            <p class="text-xs text-slate-500 leading-relaxed max-w-xl">
              Send and receive photos, gifs, videos and more. Support to dispatch high-fidelity picture files along with structured standard text blocks using the same endpoints.
            </p>
            <div class="pt-1">
              <a href="#" class="inline-flex items-center text-xs font-bold text-[#24B43C] hover:underline gap-0.5">
                Learn More <span>&rarr;</span>
              </a>
            </div>
          </div>

        </div>
      </div>
    </section>

    <section class="py-16 border-t border-slate-100 max-w-7xl mx-auto px-4 sm:px-6 lg:px-8">
      <div class="grid grid-cols-1 lg:grid-cols-12 gap-12 items-start">
        
        <div class="lg:col-span-4 space-y-4 lg:sticky lg:top-6">
          <div class="flex items-center gap-3">
            <h2 class="text-2xl font-semibold text-[#0B1A57] tracking-tight">Compliance</h2>
            <div class="w-[2px] h-6 bg-slate-200"></div>
          </div>
          <p class="text-xs sm:text-sm text-slate-500 leading-relaxed pr-4">
            Built-in local, regulatory, and explicit global security standards that liberate your team to launch fast.
          </p>
        </div>

        <div class="lg:col-span-8 grid grid-cols-1 sm:grid-cols-2 gap-x-8 gap-y-12">
          
          <div class="space-y-3">
            <div class="w-9 h-9 flex items-center justify-center rounded-lg bg-emerald-50 text-[#24B43C]">
              <svg class="w-4 h-4" fill="none" stroke="currentColor" stroke-width="2.5" viewBox="0 0 24 24">
                <path stroke-linecap="round" stroke-linejoin="round" d="M19 7l-.867 12.142A2 2 0 0116.138 21H7.862a2 2 0 01-1.995-1.858L5 7m5 4v6m4-6v6m1-10V4a1 1 0 00-1-1h-4a1 1 0 00-1 1v3M4 7h16" />
              </svg>
            </div>
            <h3 class="text-sm font-semibold text-[#0B1A57]">Message Body Purging</h3>
            <p class="text-xs text-slate-500 leading-relaxed">
              SMS message content is never permanently stored within transactional log repositories. All system request records purge natively within 30 days.
            </p>
          </div>

          <div class="space-y-3">
            <div class="w-9 h-9 flex items-center justify-center rounded-lg bg-emerald-50 text-[#24B43C]">
              <svg class="w-4 h-4" fill="none" stroke="currentColor" stroke-width="2.5" viewBox="0 0 24 24">
                <path stroke-linecap="round" stroke-linejoin="round" d="M12 15v2m-6 4h12a2 2 0 002-2v-6a2 2 0 00-2-2H6a2 2 0 00-2 2v12a2 2 0 002 2zM14 11V7a2 2 0 00-4 0v4h4z" />
              </svg>
            </div>
            <h3 class="text-sm font-semibold text-[#0B1A57]">Protect Sensitive Data</h3>
            <p class="text-xs text-slate-500 leading-relaxed">
              Regulated healthcare platforms rely heavily on our isolated environments. Safely disable debug tracking or mask user telephone numbers dynamically.
            </p>
          </div>

          <div class="space-y-3">
            <div class="w-9 h-9 flex items-center justify-center rounded-lg bg-emerald-50 text-[#24B43C]">
              <svg class="w-4 h-4" fill="none" stroke="currentColor" stroke-width="2.5" viewBox="0 0 24 24">
                <path stroke-linecap="round" stroke-linejoin="round" d="M12 8v4l3 3m6-3a9 9 0 11-18 0 9 9 0 0118 0z" />
              </svg>
            </div>
            <h3 class="text-sm font-semibold text-[#0B1A57]">Smart Rate Limiting</h3>
            <p class="text-xs text-slate-500 leading-relaxed">
              Stay fully compliant with localized volume thresholds and carrier rules automatically enforced across individual destination endpoints.
            </p>
          </div>

          <div class="space-y-3">
            <div class="w-9 h-9 flex items-center justify-center rounded-lg bg-emerald-50 text-[#24B43C]">
              <svg class="w-4 h-4" fill="none" stroke="currentColor" stroke-width="2.5" viewBox="0 0 24 24">
                <path stroke-linecap="round" stroke-linejoin="round" d="M10 14l2-2m0 0l2-2m-2 2l-2-2m2 2l2 2m7-2a9 9 0 11-18 0 9 9 0 0118 0z" />
              </svg>
            </div>
            <h3 class="text-sm font-semibold text-[#0B1A57]">Automatic Opt-out Handling</h3>
            <p class="text-xs text-slate-500 leading-relaxed">
              System intent handlers safely intercept matching inbound keywords like "STOP" or "CANCEL" to manage blocking matrices systematically.
            </p>
          </div>

        </div>
      </div>
    </section>

    <section class="py-16 border-t border-slate-100 max-w-7xl mx-auto px-4 sm:px-6 lg:px-8">
      <div class="grid grid-cols-1 lg:grid-cols-12 gap-12 items-start">
        
        <div class="lg:col-span-4 space-y-4 lg:sticky lg:top-6">
          <div class="flex items-center gap-3">
            <h2 class="text-2xl font-semibold text-[#0B1A57] tracking-tight">Improved Message Delivery</h2>
            <div class="w-[2px] h-12 bg-slate-200"></div>
          </div>
          <p class="text-xs sm:text-sm text-slate-500 leading-relaxed pr-4">
            Quality-based carrier routing engine optimizations ensuring top transactional deliverability across international networks.
          </p>
        </div>

        <div class="lg:col-span-8 grid grid-cols-1 sm:grid-cols-2 gap-x-8 gap-y-12">
          
          <div class="space-y-3">
            <div class="w-9 h-9 flex items-center justify-center rounded-lg bg-amber-50 text-amber-600">
              <svg class="w-4 h-4" fill="none" stroke="currentColor" stroke-width="2.5" viewBox="0 0 24 24">
                <path stroke-linecap="round" stroke-linejoin="round" d="M10 20l4-16m4 4l4 4-4 4M6 16l-4-4 4-4" />
              </svg>
            </div>
            <h3 class="text-sm font-semibold text-[#0B1A57]">Intelligent Message Encoding</h3>
            <p class="text-xs text-slate-500 leading-relaxed">
              We intercept unsupported Unicode text streams and adapt matching fallback characters to guarantee delivery across non-compliant target destinations.
            </p>
          </div>

          <div class="space-y-3">
            <div class="w-9 h-9 flex items-center justify-center rounded-lg bg-amber-50 text-amber-600">
              <svg class="w-4 h-4" fill="none" stroke="currentColor" stroke-width="2.5" viewBox="0 0 24 24">
                <path stroke-linecap="round" stroke-linejoin="round" d="M17 20h5v-2a3 3 0 00-5.356-1.857M17 20H7m10 0v-2c0-.656-.126-1.283-.356-1.857M7 20H2v-2a3 3 0 015.356-1.857M7 20v-2c0-.656.126-1.283.356-1.857m0 0a5.002 5.002 0 019.288 0M15 7a3 3 0 11-6 0 3 3 0 016 0zm6 3a2 2 0 11-4 0 2 2 0 014 0zM7 10a2 2 0 11-4 0 2 2 0 014 0z" />
              </svg>
            </div>
            <h3 class="text-sm font-semibold text-[#0B1A57]">Number Pooling</h3>
            <p class="text-xs text-slate-500 leading-relaxed">
              Distribute outward delivery volumes flawlessly among automated sets of phone numbers to avoid packet traffic blockages.
            </p>
          </div>

          <div class="space-y-3">
            <div class="w-9 h-9 flex items-center justify-center rounded-lg bg-amber-50 text-amber-600">
              <svg class="w-4 h-4" fill="none" stroke="currentColor" stroke-width="2.5" viewBox="0 0 24 24">
                <path stroke-linecap="round" stroke-linejoin="round" d="M13 7h8m0 0v8m0-8l-8 8-4-4-6 6" />
              </svg>
            </div>
            <h3 class="text-sm font-semibold text-[#0B1A57]">Conversion API</h3>
            <p class="text-xs text-slate-500 leading-relaxed">
              Real-time programmatic system checks continually direct alternative messaging routes for sustained system performance.
            </p>
          </div>

          <div class="space-y-3">
            <div class="w-9 h-9 flex items-center justify-center rounded-lg bg-amber-50 text-amber-600">
              <svg class="w-4 h-4" fill="none" stroke="currentColor" stroke-width="2.5" viewBox="0 0 24 24">
                <path stroke-linecap="round" stroke-linejoin="round" d="M17.657 16.657L13.414 20.9a1.998 1.998 0 01-2.827 0l-4.244-4.243a8 8 0 1111.314 0z" />
                <path stroke-linecap="round" stroke-linejoin="round" d="M15 11a3 3 0 11-6 0 3 3 0 016 0z" />
              </svg>
            </div>
            <h3 class="text-sm font-semibold text-[#0B1A57]">Local Match</h3>
            <p class="text-xs text-slate-500 leading-relaxed">
              Optimize response levels by dynamically serving regional outbound codes aligned directly with your recipient context.
            </p>
          </div>

        </div>
      </div>
    </section>

    <section class="py-20 border-t border-slate-100 bg-slate-50/40">
      <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8">
        
        <div class="text-center max-w-3xl mx-auto mb-16 space-y-3">
          <h2 class="text-3xl font-semibold text-[#0B1A57] tracking-tight">Faster Time to Market</h2>
          <p class="text-sm text-slate-500 leading-relaxed">
            Build, integrate, and troubleshoot connection interfaces rapidly. Focus execution cycles  on shipping native application value.
          </p>
        </div>

        <div class="grid grid-cols-1 lg:grid-cols-12 gap-12 items-start max-w-6xl mx-auto">
          
          <div class="lg:col-span-6 space-y-8">
            <div class="flex items-start gap-4">
              <div class="mt-1 flex-shrink-0 w-5 h-5 flex items-center justify-center rounded-full bg-sky-100 text-sky-600 text-xs font-bold">&checkmark;</div>
              <div class="space-y-1">
                <h3 class="text-sm font-semibold text-[#0B1A57]">Sticky Sender</h3>
                <p class="text-xs text-slate-500 leading-relaxed">Interact with consumers using the same recognizable phone layout identity over continuous session channels.</p>
              </div>
            </div>

            <div class="flex items-start gap-4">
              <div class="mt-1 flex-shrink-0 w-5 h-5 flex items-center justify-center rounded-full bg-sky-100 text-sky-600 text-xs font-bold">&checkmark;</div>
              <div class="space-y-1">
                <h3 class="text-sm font-semibold text-[#0B1A57]">Built in Multi-tenancy</h3>
                <p class="text-xs text-slate-500 leading-relaxed">Segment customer nodes based on active data scope, volume parameters, or profile configurations with sub-accounts.</p>
              </div>
            </div>

            <div class="flex items-start gap-4">
              <div class="mt-1 flex-shrink-0 w-5 h-5 flex items-center justify-center rounded-full bg-sky-100 text-sky-600 text-xs font-bold">&checkmark;</div>
              <div class="space-y-1">
                <h3 class="text-sm font-semibold text-[#0B1A57]">Detailed Debug Logs</h3>
                <p class="text-xs text-slate-500 leading-relaxed">Isolate gateway delivery glitches quickly using descriptive console request traces built straight inside your view models.</p>
              </div>
            </div>
          </div>

          <div class="lg:col-span-6 space-y-8">
            <div class="bg-slate-900 rounded-xl p-6 shadow-xl border border-slate-800 font-mono text-[11px] text-slate-400 space-y-2">
              <div class="text-slate-500 text-xs font-sans pb-2 border-b border-slate-800 flex items-center justify-between">
                <span>SDK Core Controller</span>
                <span class="text-emerald-400">v3.4.1</span>
              </div>
              <div><span class="text-purple-400">import</span> Flowdacity <span class="text-purple-400">from</span> <span class="text-emerald-400">'@Flowdacity/sdk'</span>;</div>
              <div><span class="text-purple-400">const</span> client = <span class="text-purple-400">new</span> Flowdacity.<span class="text-sky-400">Client</span>(process.env.AUTH_ID);</div>
              <div class="text-slate-500 pt-1"> Dispatched instantly via localized edge clusters</div>
              <div>client.messages.<span class="text-sky-400">create</span>({ src: <span class="text-amber-300">'10DLC'</span>, text: <span class="text-amber-300">'Verified'</span> });</div>
            </div>

            <div class="grid grid-cols-1 sm:grid-cols-2 gap-6 pt-2">
              <div class="space-y-1">
                <h4 class="text-xs font-bold text-[#0B1A57] uppercase tracking-wide">Extensive Docs</h4>
                <p class="text-[11px] text-slate-500 leading-relaxed">Deploy templates into runtime applications smoothly using ready-made boilerplate configurations.</p>
              </div>
              <div class="space-y-1">
                <h4 class="text-xs font-bold text-[#0B1A57] uppercase tracking-wide">Server Side SDKs</h4>
                <p class="text-[11px] text-slate-500 leading-relaxed">Full environment integrations configured naturally for Node.js, Python, Ruby, Go, Java, and C#.</p>
              </div>
            </div>
          </div>

        </div>
      </div>
    </section>

    <section class="bg-slate-900 text-white py-16 text-center rounded-2xl max-w-6xl mx-auto my-16 px-6 shadow-xl relative overflow-hidden">
      <div class="absolute inset-0 bg-[radial-gradient(circle_at_top_right,_var(--tw-gradient-stops))] from-blue-950/40 via-transparent to-transparent pointer-events-none"></div>
      
      <div class="relative z-10 max-w-2xl mx-auto space-y-6">
        <h2 class="text-2xl sm:text-3xl font-semibold tracking-tight text-white">
          It's easy to get started. Sign up for free.
        </h2>
        <p class="text-slate-400 text-xs sm:text-sm font-normal">
          Create your account and receive trial credits or get in touch with our solutions engineers today.
        </p>
        <div class="flex flex-wrap items-center justify-center gap-4 pt-4">
          <button class="px-6 py-3 bg-[#24B43C] hover:bg-[#1e9632] text-white font-semibold text-xs tracking-wider uppercase rounded transition duration-150 shadow-md shadow-emerald-950/50">
            GET STARTED 
          </button>
          <button class="px-6 py-3 border border-slate-700 text-slate-200 hover:text-white hover:bg-slate-800 font-semibold text-xs tracking-wider uppercase rounded transition duration-150">
            TALK TO AN EXPERT
          </button>
        </div>
      </div>
    </section>

    </div>
      </div>
      <div v-show="activeTab === 'shortcode'" class="space-y-20">
  <div class="bg-white text-gray-700 font-sans antialiased selection:bg-blue-100">

    <section class="text-center py-16 max-w-4xl mx-auto px-4">
      <h2 class="text-5xl font-bold text-gray-900 mb-4">Short Code</h2>
      <p class="text-xl text-gray-600 mb-8">Send messages at high throughput volumes globally using a 5 or 6 digit number.</p>
      <div class="flex items-center justify-center gap-4">
        <button class="px-8 py-3 bg-blue-900 text-white font-bold rounded hover:bg-blue-800 transition">
          GET STARTED NOW
        </button>
        <button class="px-8 py-3 border-2 border-gray-900 text-gray-900 font-bold rounded hover:bg-gray-900 hover:text-white transition">
          TALK TO AN EXPERT
        </button>
      </div>
    </section>

    <section class="py-16 border-t border-gray-200 max-w-7xl mx-auto px-4 sm:px-6 lg:px-8">
      <div class="grid grid-cols-1 lg:grid-cols-12 gap-12">
        <div class="lg:col-span-4 space-y-4">
          <div class="flex items-center gap-4">
            <h2 class="text-3xl font-bold text-gray-900 leading-tight">Random vs Vanity<br/>Short Codes</h2>
            <div class="w-1 h-12 bg-gray-300 hidden lg:block"></div>
          </div>
          <p class="text-gray-500 text-sm">Choose the provisioning approach that aligns with your campaign goals.</p>
        </div>

        <div class="lg:col-span-8 grid grid-cols-1 md:grid-cols-2 gap-8">
          <div class="space-y-4">
            <h3 class="text-xl font-bold text-gray-900">Random Short Code</h3>
            <p class="text-gray-600 leading-relaxed text-sm">
              A 5 or 6 digit number that is assigned to you randomly by wireless carriers. This is best suited for shipping notifications, two-factor authentication, or general alerts.
            </p>
            <div class="pt-2">
              <span class="text-[10px] font-mono font-bold tracking-wider text-gray-400 block mb-1">EXAMPLE</span>
              <span class="text-2xl font-mono font-bold bg-gray-100 px-4 py-1.5 rounded text-gray-900 inline-block">84345</span>
            </div>
          </div>

          <div class="space-y-4">
            <h3 class="text-xl font-bold text-gray-900">Vanity Short Code</h3>
            <p class="text-gray-600 leading-relaxed text-sm">
              A 5 or 6 digit number that you specifically choose. You can choose a number that represents your brand or is easy for your customers to remember for marketing campaigns.
            </p>
            <div class="pt-2">
              <span class="text-[10px] font-mono font-bold tracking-wider text-gray-400 block mb-1">EXAMPLE</span>
              <span class="text-2xl font-mono font-bold bg-green-50 border border-green-200 px-4 py-1.5 rounded text-green-700 inline-block">77777</span>
            </div>
          </div>
        </div>
      </div>
    </section>

    <section class="py-16 border-t border-gray-200 max-w-7xl mx-auto px-4 sm:px-6 lg:px-8">
      <div class="grid grid-cols-1 lg:grid-cols-12 gap-12">
        <div class="lg:col-span-4">
          <div class="flex items-start gap-4">
            <h2 class="text-3xl font-bold text-gray-900 leading-tight">Benefits of Dedicated<br/>Short Code</h2>
            <div class="w-1 h-12 bg-gray-300 hidden lg:block"></div>
          </div>
        </div>

        <div class="lg:col-span-8 grid grid-cols-1 md:grid-cols-2 gap-x-8 gap-y-12">
          <div class="space-y-2">
            <h3 class="text-lg font-bold text-gray-900">High Throughput Rate</h3>
            <p class="text-gray-600 text-sm">Send massive amounts of messages instantly. Short codes are approved by wireless carriers for high volume throughput up to 100 messages per second by default.</p>
          </div>

          <div class="space-y-2">
            <h3 class="text-lg font-bold text-gray-900">Higher Open Rates</h3>
            <p class="text-gray-600 text-sm">Short codes are easy to remember, which builds trust with consumers and improves interaction metrics and read rates significantly over long codes.</p>
          </div>

          <div class="space-y-2">
            <h3 class="text-lg font-bold text-gray-900">Two-Way Messaging</h3>
            <p class="text-gray-600 text-sm">Receive replies and handle customer responses seamlessly. Perfect for marketing keywords like text "JOIN" to get automatic updates.</p>
          </div>

          <div class="space-y-2">
            <h3 class="text-lg font-bold text-gray-900">Carrier Approved</h3>
            <p class="text-gray-600 text-sm">Short codes are individually pre-registered and provisioned with carriers, shielding your marketing campaigns against spam filtration algorithms.</p>
          </div>
        </div>
      </div>
    </section>

    <section class="py-16 border-t border-gray-200 bg-gray-50/50">
      <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8">
        <div class="text-center max-w-2xl mx-auto mb-12">
          <h2 class="text-3xl font-bold text-gray-900 tracking-tight">Industries Using Short Codes</h2>
          <p class="text-gray-600 text-sm mt-2">Discover how different sectors leverage high-volume text streams effectively.</p>
        </div>

        <div class="grid grid-cols-1 md:grid-cols-3 gap-8">
          <div class="bg-white p-6 rounded-lg border border-gray-200 shadow-sm space-y-3">
            <div class="w-10 h-10 bg-blue-50 text-blue-900 rounded flex items-center justify-center font-bold">🛒</div>
            <h3 class="text-lg font-bold text-gray-900">Retail & E-commerce</h3>
            <p class="text-gray-600 text-sm leading-relaxed">Flash sales, personalized discount vouchers, cart abandonment recovery alerts, and real-time delivery status tracking messages.</p>
          </div>

          <div class="bg-white p-6 rounded-lg border border-gray-200 shadow-sm space-y-3">
            <div class="w-10 h-10 bg-blue-50 text-blue-900 rounded flex items-center justify-center font-bold">🏦</div>
            <h3 class="text-lg font-bold text-gray-900">Banking & Finance</h3>
            <p class="text-gray-600 text-sm leading-relaxed">Instant multi-factor validation tokens (OTP), fraud detection warning flags, balance updates, and immediate transaction logs.</p>
          </div>

          <div class="bg-white p-6 rounded-lg border border-gray-200 shadow-sm space-y-3">
            <div class="w-10 h-10 bg-blue-50 text-blue-900 rounded flex items-center justify-center font-bold">📦</div>
            <h3 class="text-lg font-bold text-gray-900">Logistics & Delivery</h3>
            <p class="text-gray-600 text-sm leading-relaxed">Driver-to-customer notification triggers, localized drop-off completion notices, and instant verification signature requests.</p>
          </div>
        </div>
      </div>
    </section>

    <section class="py-16 border-t border-gray-200 max-w-7xl mx-auto px-4 sm:px-6 lg:px-8">
      <div class="text-center max-w-2xl mx-auto mb-12">
        <h2 class="text-3xl font-bold text-gray-900 tracking-tight">Transparent Short Code Pricing</h2>
        <p class="text-gray-600 text-sm mt-2">Clear lease and setup fee structures with no hidden maintenance surcharges.</p>
      </div>

      <div class="grid grid-cols-1 md:grid-cols-2 gap-8 max-w-4xl mx-auto">
        <div class="border border-gray-200 rounded-xl p-8 bg-white shadow-sm flex flex-col justify-between">
          <div class="space-y-4">
            <h3 class="text-xl font-bold text-gray-900">Random Short Code Lease</h3>
            <p class="text-gray-500 text-xs">Assigned dynamically by wireless carrier systems.</p>
            <div class="py-4 border-y border-gray-100">
              <span class="text-4xl font-bold text-gray-900">$500</span>
              <span class="text-gray-500 text-sm font-medium"> / month</span>
            </div>
            <ul class="space-y-2.5 text-sm text-gray-600 pt-2">
              <li class="flex items-center gap-2"><span class="text-blue-900 font-bold">&checkmark;</span> $500 Carrier setup setup fee</li>
              <li class="flex items-center gap-2"><span class="text-blue-900 font-bold">&checkmark;</span> 3-6 weeks provisioning baseline</li>
              <li class="flex items-center gap-2"><span class="text-blue-900 font-bold">&checkmark;</span> Dedicated application routing loops</li>
            </ul>
          </div>
          <button class="w-full mt-8 py-3 border border-gray-900 text-gray-900 font-bold rounded hover:bg-gray-900 hover:text-white transition text-xs uppercase tracking-wider">Lease Random Code</button>
        </div>

        <div class="border-2 border-blue-900 rounded-xl p-8 bg-white shadow-md flex flex-col justify-between relative">
          <div class="absolute -top-3 left-1/3 right-1/3 bg-blue-900 text-white text-[10px] font-bold uppercase tracking-widest py-1 rounded-full text-center">Most Popular</div>
          <div class="space-y-4">
            <h3 class="text-xl font-bold text-gray-900">Vanity Short Code Lease</h3>
            <p class="text-gray-500 text-xs">Custom picked specific number combinations.</p>
            <div class="py-4 border-y border-gray-100">
              <span class="text-4xl font-bold text-gray-900">$1,000</span>
              <span class="text-gray-500 text-sm font-medium"> / month</span>
            </div>
            <ul class="space-y-2.5 text-sm text-gray-600 pt-2">
              <li class="flex items-center gap-2"><span class="text-blue-900 font-bold">&checkmark;</span> $500 Carrier setup setup fee</li>
              <li class="flex items-center gap-2"><span class="text-blue-900 font-bold">&checkmark;</span> Choose custom matching strings</li>
              <li class="flex items-center gap-2"><span class="text-blue-900 font-bold">&checkmark;</span> Maximum consumer recall visibility</li>
            </ul>
          </div>
          <button class="w-full mt-8 py-3 bg-blue-900 text-white font-bold rounded hover:bg-blue-800 transition text-xs uppercase tracking-wider">Lease Vanity Code</button>
        </div>
      </div>
    </section>

    <section class="py-16 border-t border-gray-200 bg-gray-50">
      <div class="max-w-3xl mx-auto px-4">
        <div class="text-center mb-10 space-y-2">
          <h2 class="text-3xl font-bold text-gray-900">Apply for a Dedicated Short Code</h2>
          <p class="text-gray-600 text-sm">Fill out your messaging use case and our provisioning team will handle carrier registry execution.</p>
        </div>

        <form @submit.prevent class="bg-white border border-gray-200 rounded-xl p-8 shadow-sm space-y-6">
          <div class="grid grid-cols-1 md:grid-cols-2 gap-6">
            <div class="space-y-1.5">
              <label class="text-xs font-bold text-gray-700 uppercase tracking-wide">First Name</label>
              <input type="text" placeholder="John" class="w-full border border-gray-300 rounded px-4 py-2.5 text-sm focus:outline-none focus:border-blue-900 transition" />
            </div>
            <div class="space-y-1.5">
              <label class="text-xs font-bold text-gray-700 uppercase tracking-wide">Last Name</label>
              <input type="text" placeholder="Doe" class="w-full border border-gray-300 rounded px-4 py-2.5 text-sm focus:outline-none focus:border-blue-900 transition" />
            </div>
          </div>

          <div class="space-y-1.5">
            <label class="text-xs font-bold text-gray-700 uppercase tracking-wide">Business Email</label>
            <input type="email" placeholder="john@company.com" class="w-full border border-gray-300 rounded px-4 py-2.5 text-sm focus:outline-none focus:border-blue-900 transition" />
          </div>

          <div class="space-y-1.5">
            <label class="text-xs font-bold text-gray-700 uppercase tracking-wide">Short Code Type Preferred</label>
            <select class="w-full border border-gray-300 rounded bg-white px-4 py-2.5 text-sm focus:outline-none focus:border-blue-900 transition">
              <option>Random Short Code ($500/mo)</option>
              <option>Vanity Short Code ($1,000/mo)</option>
            </select>
          </div>

          <div class="space-y-1.5">
            <label class="text-xs font-bold text-gray-700 uppercase tracking-wide">Estimated Monthly Volume</label>
            <input type="text" placeholder="e.g., 500,000 messages/mo" class="w-full border border-gray-300 rounded px-4 py-2.5 text-sm focus:outline-none focus:border-blue-900 transition" />
          </div>

          <div class="space-y-1.5">
            <label class="text-xs font-bold text-gray-700 uppercase tracking-wide">Brief Campaign Description</label>
            <textarea rows="4" placeholder="Describe how end-users opt-in and what type of alert tokens or marketing updates you plan to distribute..." class="w-full border border-gray-300 rounded px-4 py-2.5 text-sm focus:outline-none focus:border-blue-900 transition"></textarea>
          </div>

          <button type="submit" class="w-full py-3 bg-green-600 hover:bg-green-700 text-white font-bold rounded transition text-xs uppercase tracking-wider shadow-sm">
            Submit Provisioning Request
          </button>
        </form>
      </div>
    </section>

    <section class="text-center py-16 max-w-5xl mx-auto px-4">
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