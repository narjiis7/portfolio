<script lang="ts">
  import { onMount } from 'svelte';
  import gsap from 'gsap';
  import lottie from 'lottie-web';

  onMount(() => {
    lottie.loadAnimation({
      container: document.querySelector('#web-development') as Element,
      renderer: 'svg',
      loop: true,
      autoplay: true,
      path: '/web development.json'
    });
  });

  let activeSection = 'home';

  onMount(() => {
    gsap.set('.skills-title', { opacity: 0, y: 40 });
    gsap.set('.skill-item', { opacity: 0, x: -30 });

    gsap.to('.skills-title', {
      opacity: 1,
      y: 0,
      duration: 0.8,
      ease: 'power3.out'
    });

    gsap.to('.skill-item', {
      opacity: 1,
      x: 0,
      duration: 0.6,
      ease: 'power2.out',
      stagger: 0.1
    });
  });
</script>

<!-- واجهة صفحة المهارات -->
<section class="min-h-screen flex items-center justify-center bg-linear-to-br from-gray-400 to-gray-200 px-6 py-16">
  <div class="bg-white rounded-2xl shadow-[0_8px_30px_rgba(0,0,0,0.3)] p-12 w-full max-w-6xl flex flex-col md:flex-row gap-12 items-center">

    <!-- ✅ الجهة اليسار -->
    <div class="flex-1 text-left text-teal-700 space-y-6">
      <h2 style="font-family: 'EB Garamond', serif" class="text-5xl font-bold skills-title">
        My Skills
      </h2>

      <ul class="list-inside text-gray-700 text-lg space-y-3">
        <li class="skill-item animate__animated animate__backInLeft animate__delay-10s">
          <i class="devicon-html5-plain colored text-2xl mr-3"></i> HTML
        </li>
        <li class="skill-item animate__animated animate__backInLeft animate__delay-20s">
          <i class="devicon-css3-plain colored text-2xl mr-3"></i> CSS
        </li>
        <li class="skill-item animate__animated animate__backInLeft animate__delay-30s">
          <i class="devicon-javascript-plain colored text-2xl mr-3"></i> JavaScript
        </li>
        <li class="skill-item animate__animated animate__backInLeft animate__delay-40s">
          <i class="devicon-typescript-plain colored text-2xl mr-3"></i> TypeScript
        </li>
        <li class="skill-item animate__animated animate__backInLeft animate__delay-50s">
          <i class="devicon-cplusplus-plain colored text-2xl mr-3"></i> C++
        </li>
        <li class="skill-item animate__animated animate__backInLeft animate__delay-60s">
          <i class="devicon-php-plain colored text-2xl mr-3"></i> Basic PHP
        </li>
        <li class="skill-item animate__animated animate__backInLeft animate__delay-7s">
          <i class="devicon-csharp-plain colored text-2xl mr-3"></i> C#
        </li>
        <li class="skill-item animate__animated animate__backInLeft animate__delay-8s">
          <i class="devicon-svelte-plain colored text-2xl mr-3"></i> Svelte
        </li>
        <li class="skill-item animate__animated animate__backInLeft animate__delay-9s">
          <i class="devicon-tailwindcss-plain colored text-2xl mr-3"></i> Tailwind CSS
        </li>
        <li class="skill-item animate__animated animate__backInLeft animate__delay-10s">
          <i class="devicon-gsap-plain colored text-2xl mr-3"></i> GSAP Animations
        </li>
      </ul>
    </div>

    <!-- ✅ الجهة اليمين -->
    <div class="flex-1 text-center text-purple-700 space-y-6">
 
      <div id="web-development" class="w-88 h-88 mx-auto"></div>
    </div>

  </div>
</section>