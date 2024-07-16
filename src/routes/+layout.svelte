<script lang="ts">
  import Navbar from '$lib/components/Navbar.svelte';
  import { cubicIn, cubicOut } from 'svelte/easing';
  import '../app.pcss';
  import { fade } from 'svelte/transition';
  import { Toaster } from '$lib/components/ui/sonner';

  export let data;
</script>

<Toaster />
<Navbar />
{#key data.pathname}
  <main
    in:fade={{ easing: cubicOut, duration: 300, delay: 400 }}
    out:fade={{ easing: cubicIn, duration: 300 }}
  >
    <slot />
  </main>
{/key}
