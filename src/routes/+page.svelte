<script lang="ts">
  import { fade } from 'svelte/transition';

  const promise = new Promise((resolve) => {
    setTimeout(() => {
      resolve(true);
    }, 2000);
  });
</script>

{#await promise}
  <!--  -->
{:then value}
  {#if value}
    <button in:fade={{ duration: 2000 }}> This is a button </button>
  {/if}
{/await}
