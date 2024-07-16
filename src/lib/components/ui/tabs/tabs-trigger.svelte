<script lang="ts">
  import { Tabs as TabsPrimitive } from 'bits-ui';
  import { cn } from '$lib/utils.js';

  type $$Props = TabsPrimitive.TriggerProps;
  type $$Events = TabsPrimitive.TriggerEvents;

  let className: $$Props['class'] = undefined;
  export let value: $$Props['value'];
  export { className as class };
</script>

<TabsPrimitive.Trigger
  class={cn(
    'inline-flex items-center justify-center whitespace-nowrap text-balance rounded-lg bg-[#27272c] p-3 font-medium text-white ring-offset-white transition-all focus-visible:outline-none focus-visible:ring-2 focus-visible:ring-ring focus-visible:ring-offset-2 disabled:pointer-events-none disabled:opacity-50 data-[state=active]:bg-accent data-[state=active]:font-bold data-[state=active]:text-primary data-[state=active]:shadow-sm',
    className
  )}
  {value}
  {...$$restProps}
  on:click
>
  <slot />
</TabsPrimitive.Trigger>
