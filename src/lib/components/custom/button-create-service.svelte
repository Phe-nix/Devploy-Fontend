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

<!-- <DropdownMenu.Root>
  <DropdownMenu.Trigger>
    <Button class="gap-3 font-normal">
      <Computer class="size-6" />
      Create Services
    </Button>
  </DropdownMenu.Trigger>
  <DropdownMenu.Content transition={flyAndScale} sideOffset={8}>
    <DropdownMenu.Group>
      <DropdownMenu.Item>
        <a class="flex gap-3 items-center" href="/home/project/1/new/service">
          <Server class="size-4" />
          Appications
        </a>
      </DropdownMenu.Item>
      <DropdownMenu.Item>
        <a class="flex gap-3 items-center" href="/home/project/1/new/database">
            <Database class="size-4" />
            Databases
        </a>
      </DropdownMenu.Item>
    </DropdownMenu.Group>
  </DropdownMenu.Content>
</DropdownMenu.Root> -->

{#if type == 'application'}
<Button on:click={() => {
  goto('/home/new/service')
}} class={cn("gap-3 font-normal", className)}>
  <Server class="size-6" />
  Create Applications
</Button>
{:else if type == 'database'}
<Button on:click={() => {
  goto('/home/new/database')
}} class={cn("gap-3 font-normal", className)}>
  <Database class="size-6" />
  Create Databases
</Button>
{:else}
<div></div>
{/if}