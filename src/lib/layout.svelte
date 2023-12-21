<script lang="ts">
  export let title: string;
  export let id: string;
</script>

<div class="sm:p-0 p-5" {id}>
  <div class="2xl:w-8/12 mx-auto py-10">
    <h1
      class="2xl:text-3xl text-2xl font-bold mb-5 border-l-4 ps-2 border-slate-600"
    >
      {title}
    </h1>
    <slot />
  </div>
</div>
