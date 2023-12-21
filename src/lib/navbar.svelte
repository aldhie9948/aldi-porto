<script lang="ts">
  import Icon from "@iconify/svelte";
  import { onMount } from "svelte";
  let showMenu: boolean = true;
  const toggleMenu = () => (showMenu = !showMenu);
  onMount(() => {
    if (window.innerWidth < 800) showMenu = false;
  });
</script>

<nav
  class="flex sm:flex-nowrap flex-wrap gap-2 items-center px-8 py-5 justify-center"
>
  <Icon icon="ph:code-bold" class="text-lg" />
  <p class="flex-grow font-semibold">Porto Aldi</p>
  <button on:click={toggleMenu} class="sm:hidden block">
    <Icon
      icon="icon-park-outline:application-menu"
      class="text-2xl hover:opacity-70 active:opacity-100"
    />
  </button>
  {#if showMenu}
    <div class="flex sm:flex-row flex-col sm:w-fit w-full gap-2 items-center">
      <a href="#work" class="link">work</a>
      <a href="#services" class="link">services</a>
      <a href="#about" class="link">contact</a>
    </div>
  {/if}
</nav>

<style lang="scss">
  .link {
    @apply px-5 font-light border-b-2 border-transparent hover:border-slate-500 duration-200 active:opacity-60;
  }
</style>
