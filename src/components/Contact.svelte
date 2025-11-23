<script lang="ts">
  import { onMount } from 'svelte';
  import QRCode from 'qrcode';

  let qrSrc = '';
  const cvLink = 'http://localhost:5173/cv.pdf';

  onMount(async () => {
    qrSrc = await QRCode.toDataURL(cvLink);
  });
</script>



<section class="min-h-screen flex items-center justify-center bg-gray-300 px-6 py-12">
  <div class="bg-white rounded-2xl shadow-[0_8px_30px_rgba(0,0,0,0.3)] p-12 w-full max-w-6xl flex flex-col md:flex-row gap-12 items-center">

    <!-- ✅ الجهة اليسرى: طرق التواصل -->
    <div class="flex-1 space-y-6 text-teal-700 contact-item">
      <h2 class="text-4xl font-bold">Contact Info</h2>
      <p class="text-lg flex items-center gap-3">
        <i class="fa-solid fa-phone text-black-600"></i> +964 770 000 0000
      </p>
      <p class="text-lg flex items-center gap-3">
        <i class="fa-solid fa-envelope text-black-600"></i> youremail@example.com
      </p>
      <p class="text-lg flex items-center gap-3">
        <i class="fa-brands fa-linkedin text-blue-600"></i>
        <a href="https://linkedin.com/in/yourprofile" target="_blank" class="hover:underline">LinkedIn Profile</a>
      </p>
      <p class="text-lg flex items-center gap-3">
        <i class="fa-brands fa-github text-gray-800"></i>
        <a href="https://github.com/yourprofile" target="_blank" class="hover:underline">GitHub Profile</a>
      </p>
      
    </div>

    <!-- ✅ الجهة اليمنى: QR Code للـ CV -->
    <div class="flex-1 flex justify-center contact-item">
      {#if qrSrc}
        <a href={cvLink} target="_blank">
          <img src={qrSrc} alt="QR Code"
               class="w-[20rem] h-80 shadow-xl rounded-2xl border border-gray-200 hover:scale-105 transition"/>
        </a>
      {/if}
    </div>

  </div>
</section>