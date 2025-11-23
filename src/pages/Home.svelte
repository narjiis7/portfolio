<script>
  import { onMount } from 'svelte';
  import gsap from 'gsap';

  let activeSection = 'home';

  onMount(() => {
    // نضمن إن كل الحروف تبدأ مخفية ومتحركة من البداية
    gsap.set('.hero-letter', {
      opacity: 0,
      x: -30,
      y: 40
    });

    // ثم نعمل الأنيميشن
    gsap.to('.hero-letter', {
      opacity: 1,
      x: 0,
      y: 0,
      duration: 0.8,
      ease: 'power3.out',
      stagger: 0.05
    });
  });
</script>
<div> 
<script>
  let activeSection = 'home';
   
</script>
</div>
<!-- Sidebar يبقى مثل ما هو -->

<section class="min-h-screen bg-linear-to-br from-gray-600 flex items-center justify-center px-6 py-12">
  <div class="bg-white rounded-2xl shadow-[0_8px_30px_rgba(0,0,0,0.3)] p-8 w-full max-w-6xl flex gap-8">

    <!-- ✅ المربع الوردي داخل الكارت -->
    <div class="bg-teal-500 rounded-lg shadow-md p-4 w-44 flex flex-col gap-10">
      <img src="myphoto.jpeg"  alt="ph" class="w-48 h-48 rounded-full object-cover border-4 border-red-100 shadow-lg hero-item" />
      <a
        href="#home"
        on:click={() => activeSection = 'home'}
          class="font-bold transform transition hover:scale-110"
        class:underline={activeSection === 'home'}
         >
         
        Home 🏠
      </a>
          
        
      <a
        href="#about"
        on:click={() => activeSection = 'about'}
        class="font-bold transform transition hover:scale-110"
        class:underline={activeSection === 'about'}
      >
        About 🙋‍♀️
      </a>
      <a
        href="#projects"
        on:click={() => activeSection = 'projects'}
        class="font-bold transform transition hover:scale-110"
        class:underline={activeSection === 'projects'}
      >
        Projects 💼
      </a>
      <a
        href="#contact"
        on:click={() => activeSection = 'contact'}
        class="font-bold transform transition hover:scale-110"
        class:underline={activeSection === 'contact'}
      >
        Contact 📞
      </a>
    </div>
    <!-- ✅ المحتوى الرئيسي داخل الكارت -->
    <div class="flex-1 text-teal-700 space-y-6 text-center">
  <h1 id="home" style="font-family: 'EB Garamond', serif;" class="text-5xl md:text-7xl font-bold">
    HI THERE !
  </h1>

  <h1 style="font-family: 'EB Garamond', serif;" class="text-5xl md:text-6xl font-bold max-h-dvh flex justify-center flex-wrap gap-1">
    {#each 'Welcome to my portfolio'.split('') as char}
      <span class="hero-letter text-teal-700">{char === ' ' ? '\u00A0' : char}</span>
    {/each}
  </h1>

  <h1 style="font-family: 'EB Garamond', serif;" class="text-4xl md:text-4xl font-bold flex justify-center flex-wrap gap-1">
    {#each 'created by Narjis Eehab'.split('') as char}
      <span class="hero-letter text-teal-700">{char === ' ' ? '\u00A0' : char}</span>
    {/each}
  </h1>
</div></section>