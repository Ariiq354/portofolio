<script lang="ts">
  import { page } from '$app/stores';
  import { cn } from '$lib/utils';
  import { Button } from '$lib/components/ui/button';
  import * as Sheet from '$lib/components/ui/sheet';
  import { AlignRight } from 'lucide-svelte';

  let isOpen = false;

  const pathname = [
    {
      name: 'home',
      path: '/'
    },
    {
      name: 'resume',
      path: '/resume'
    },
    {
      name: 'work',
      path: '/work'
    },
    {
      name: 'contact',
      path: '/contact'
    }
  ];
</script>

<header class="py-8 xl:py-12">
  <div class="container mx-auto flex items-center justify-between">
    <a href="/">
      <h1 class="text-4xl font-semibold">
        Ariiq<span class="text-accent">.</span>
      </h1>
    </a>

    <!-- Desktop -->
    <div class="hidden items-center gap-8 xl:flex">
      <nav class="flex gap-8">
        {#each pathname as item}
          <a
            href={item.path}
            class={cn(
              $page.url.pathname === item.path ? 'border-b-2 border-accent text-accent' : '',
              'font-medium capitalize transition-all hover:text-accent'
            )}
          >
            {item.name}
          </a>
        {/each}
      </nav>
      <a href="/contact">
        <Button class="rounded-full bg-accent text-primary hover:bg-accent/90">Hire me</Button>
      </a>
    </div>

    <!-- Mobile -->
    <div class="xl:hidden">
      <Sheet.Root open={isOpen} onOpenChange={(open) => (isOpen = open)}>
        <Sheet.Trigger class="flex items-center justify-center" aria-label="menu">
          <AlignRight class="text-[32px] text-accent" />
        </Sheet.Trigger>
        <Sheet.Content>
          <Sheet.Header>
            <Sheet.Title class="text-left text-white">
              <h1 class="text-lg font-semibold">
                Ariiq<span class="text-accent">.</span>
              </h1>
            </Sheet.Title>
          </Sheet.Header>
          <nav class="mt-4 flex flex-col items-center justify-center gap-2">
            {#each pathname as item}
              <a
                href={item.path}
                class={cn(
                  ' capitalize transition-all hover:text-accent',
                  $page.url.pathname === item.path ? 'border-b-2 border-accent text-accent' : ''
                )}
                on:click={() => (isOpen = false)}
              >
                {item.name}
              </a>
            {/each}
          </nav>
        </Sheet.Content>
      </Sheet.Root>
    </div>
  </div>
</header>
