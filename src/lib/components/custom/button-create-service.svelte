<script lang="ts">
  // shadcn-svelte
  import * as DropdownMenu from "$lib/components/ui/dropdown-menu";
  import { Button } from "$lib/components/ui/button/index.js";
  import { flyAndScale } from "$lib/utils";

  import { cn } from "$lib/utils.js";

  // SVG Icons
  import { Plus } from 'lucide-svelte';
  import { goto } from "$app/navigation";

  let className = '';
  export {className as class};
  export let type;
</script>

{#if type == 'application'}
<Button size="sm" on:click={() => {
  goto('/new/service')
}} class={cn("gap-3 font-normal", className)}>
  <Plus  class="size-6" />
  <p class="hidden sm:block">
    Create Applications
  </p>
</Button>
{:else if type == 'database'}
<Button size="sm" on:click={() => {
  goto('/new/database')
}} class={cn("gap-3 font-normal", className)}>
  <Plus class="size-6" />
  <p class="hidden sm:block">
    Create Databases
  </p>
</Button>
{:else}
<div></div>
{/if}