<script lang="ts">
  // shadcn-svelte
  import * as DropdownMenu from "$lib/components/ui/dropdown-menu";
  import { Button } from "$lib/components/ui/button/index.js";
  import { flyAndScale } from "$lib/utils";

  import { cn } from "$lib/utils.js";

  // SVG Icons
  import { Server } from "lucide-svelte";
  import { Database } from "lucide-svelte";
  import { goto } from "$app/navigation";

  let className = '';
  export {className as class};
  export let type;
</script>

{#if type == 'application'}
<Button on:click={() => {
  goto('/new/service')
}} class={cn("gap-3 font-normal", className)}>
  <Server class="size-6" />
  Create Applications
</Button>
{:else if type == 'database'}
<Button on:click={() => {
  goto('/new/database')
}} class={cn("gap-3 font-normal", className)}>
  <Database class="size-6" />
  Create Databases
</Button>
{:else}
<div></div>
{/if}