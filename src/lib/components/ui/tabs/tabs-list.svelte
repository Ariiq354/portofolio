<script lang="ts">
  import { Tabs as TabsPrimitive } from 'bits-ui';
  import { cn } from '$lib/utils.js';

  type $$Props = TabsPrimitive.ListProps;

  let className: $$Props['class'] = undefined;
  export { className as class };
</script>

<TabsPrimitive.List
  class={cn('inline-flex h-auto rounded-md text-primary', className)}
  {...$$restProps}
>
  <slot />
</TabsPrimitive.List>
