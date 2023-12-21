<script lang="ts">
  import { blur } from "svelte/transition";
  import profile from "../assets/image/profile.png";
  let isBioEng: boolean = true;
  const toggleBio = () => (isBioEng = !isBioEng);
</script>

<div class="bg-slate-100 sm:py-36 py-10">
  <div
    class="2xl:w-8/12 mx-auto sm:flex grid grid-cols-1 place-items-center items-center justify-center gap-5 sm:p-0 p-5"
  >
    <div
      class="sm:w-80 sm:h-80 h-96 grayscale flex-shrink-0 object-cover overflow-hidden border-2 border-slate-400"
    >
      <img src={profile} alt="aldi" />
    </div>
    <div>
      <h1 class="2xl:text-5xl text-3xl font-bold">Aldi Gunawan</h1>
      <h2 class="font-semibold">Fullstack Developer</h2>
      <hr class="border-b my-5" />
      <!-- svelte-ignore a11y-no-static-element-interactions -->
      <!-- svelte-ignore a11y-click-events-have-key-events -->
      <div
        on:dblclick={toggleBio}
        class="font-light cursor-pointer"
        title="Double Click For Switch Language"
      >
        {#if !isBioEng}
          <p in:blur class="duration-200">
            Memulai perjalanan pemrograman sejak tahun 2019, saya telah
            menguasai keterampilan dalam JavaScript, ReactJS, Svelte, Tailwind
            CSS, MySQL, MongoDB, dan React Native untuk pengembangan mobile.
            Mahir dalam menciptakan desain responsif dan ramah mobile, saya
            bersemangat untuk menghidupkan ide-ide melalui kode.
          </p>
        {:else}
          <p in:blur class="duration-200">
            Embarking on my programming journey in 2019, I've honed my skills in
            JavaScript, ReactJS, Svelte, Tailwind CSS, MySQL, MongoDB, and React
            Native for mobile development. Proficient in crafting responsive and
            mobile-friendly designs, I am passionate about bringing ideas to
            life through code.
          </p>
        {/if}
      </div>
    </div>
  </div>
</div>
