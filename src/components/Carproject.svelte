<script lang="ts">
  import { onMount } from 'svelte';
  import lottie from 'lottie-web';

  onMount(() => {
    // أنيميشن AI
    lottie.loadAnimation({
      container: document.querySelector('#engine-wheel'),
      renderer: 'svg',
      loop: true,
      autoplay: true,
      path: '/ai.json'
    });

    // أنيميشن الحاسبة
    lottie.loadAnimation({
      container: document.querySelector('#calc-animation'),
      renderer: 'svg',
      loop: true,
      autoplay: true,
      path: '/Calculator.json'
    });

    // أنيميشن الحجز
    lottie.loadAnimation({
      container: document.querySelector('#booking-animation'),
      renderer: 'svg',
      loop: true,
      autoplay: true,
      path: '/tickets.json'
    });
  });
</script>

<!-- صفحة المشاريع -->
<section class="min-h-screen flex items-center justify-center bg-gray-300 px-6 py-12">
  <div class="bg-white rounded-2xl shadow-[0_8px_30px_rgba(0,0,0,0.3)] p-10 w-full max-w-6xl flex flex-col items-center gap-10">

    <!-- العنوان -->
    <h1 class="text-3xl font-bold text-teal-700 text-center mb-6 leading-snug">
      My Projects
    </h1>

    <!-- كروت المشاريع داخل الكارت الأبيض -->
    <div class="flex flex-wrap justify-center gap-8">

      <!-- كارت AI -->
      <div class="group relative bg-white p-4 rounded-xl shadow-lg w-80 overflow-hidden hover:scale-105 transition-transform duration-300">
        <h2 class="text-xl font-bold mb-2 text-center text-teal-700">AI System</h2>
        <div id="engine-wheel" class="w-64 h-64 mx-auto"></div>
        <div class="absolute bottom-0 left-0 w-full bg-teal-600 text-white text-sm px-4 py-3 transform translate-y-full group-hover:translate-y-0 transition duration-500 ease-in-out">
          <p>🧠 Powered by Neural Networks</p>
          <p>⚙️ Real-time Data Processing</p>
          <p>📊 Predictive Analytics & Automation</p>
        </div>
      </div>

      <!-- كارت الحاسبة -->
      <div class="group relative bg-white p-4 rounded-xl shadow-lg w-80 overflow-hidden hover:scale-105 transition-transform duration-300">
        <h2 class="text-xl  mb-2 text-center font-bold text-teal-700">Simple Calculator</h2>
        <div id="calc-animation" class="w-64 h-64 mx-auto"></div>
        <div class="absolute bottom-0 left-0 w-full bg-teal-600 text-white text-sm px-4 py-3 transform translate-y-full group-hover:translate-y-0 transition duration-500 ease-in-out">
          <p>🧮 Basic Arithmetic Operations</p>
          <p>📱 Responsive UI with Svelte</p>
          <p>⚡ Fast and Lightweight</p>
        </div>
      </div>

      <!-- كارت الحجز -->
      <div class="group relative bg-white p-4 rounded-xl shadow-lg w-80 overflow-hidden hover:scale-105 transition-transform duration-300">
        <h2 class="text-xl font-bold mb-2 text-center text-teal-700">Airline Booking System</h2>
        <div id="booking-animation" class="w-64 h-64 mx-auto"></div>
        <div class="absolute bottom-0 left-0 w-full bg-teal-600 text-white text-sm px-4 py-3 transform translate-y-full group-hover:translate-y-0 transition duration-500 ease-in-out">
          <p>✈️ Real-time Flight Search</p>
          <p>🧾 Ticket Booking & Confirmation</p>
          <p>🌍 Multi-destination Support</p>
        </div>
      </div>

    </div>
  </div>
</section>