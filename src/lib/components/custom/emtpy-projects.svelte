<script lang="ts">
  // import shadcn-svelte

  // SVG Icons
  import { PackageX } from "lucide-svelte";
  import { Computer } from 'lucide-svelte';

  export let type = 'project';
</script>

{#if type === 'project'}
<div class="flex flex-col items-center space-y-2 py-48">
  <div class="border bg-card text-card-foreground p-3 rounded-lg shadow-xl">
    <PackageX class="size-8" />
  </div>
  <div class="text-lg font-semibold">You don't have any project.</div>
  <p class="text-sm text-muted-foreground">Let start project and create something new.</p>
</div>
{:else if type === 'service'}
<div class="flex flex-col items-center space-y-2 py-48">
  <div class="border bg-card text-card-foreground p-3 rounded-lg shadow-xl">
    <Computer class="size-8" />
  </div>
  <div class="text-lg font-semibold">You don't have any service.</div>
  <p class="text-sm text-muted-foreground">Let start service and create something new.</p>
</div>
{/if}
